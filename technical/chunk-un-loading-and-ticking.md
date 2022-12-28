# Chunk (un)loading & ticking

Chunk behavior has been heavily modified to accommodate for multiplayer. The modified engine aims to achieve a balance between minimizing latency lag, being efficient for the server, and providing a good gameplay experience.

{% hint style="info" %}
**Ticked** chunks refer to chunks in which the server is actively keeping track of. In ticked chunks, crops will grow, redstone will function, physics will occur, and all other game mechanics will work.\


**Unticked** chunks refer to chunks in which the server has loaded, but is not processing. While unticked chunks are visible to players, they are essentially frozen in time.
{% endhint %}

## Configuration

### Client curated

**These rules help ensure a good balance between gameplay & latency management**

* The server concurrently sends chunk data in a size of 2 chunks at a time.
* Chunks in a 2 chunk radius around clients are immediately sent to clients after teleporting.
* The server will send no more than 45 chunk's data to clients per second.
* The clients chunk view distance takes priority over the servers max view distance, if lower than the servers chunk view distance.
* The server will send up to 14 chunks in all directions to clients with respect to client view distance setting, making the maximum view distance of 448 blocks. However, only a 2 chunk radius (32 block radius) is ticked.

### Server curated

**These rules help ensure the server doesn't throttle or lag from chunk loading**

* The server will load no more than 20 chunks per second per client.
* The server will load no more than 500 chunks per second (combined amount from all clients).
* Only chunks in a 2 chunk radius (32 blocks in all directions) from the client are ticked. Chunks beyond this radius may be visible, but are inactive.

### Both

* Loaded chunks are delayed 15 seconds before unloading after they are no longer being loaded by a client. This benefits the client & server in instances where a client is teleporting between locations (ex. dying and returning) by allowing faster load times and benefits the server because it will not have to re-load all the chunks again.\
