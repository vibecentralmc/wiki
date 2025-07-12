# Chunk behavior

Chunk behavior has been heavily modified to accommodate multiplayer. Our modifications aim to achieve a balance between minimizing latency lag, providing a good gameplay experience, and being computationally capable for the server.

{% hint style="info" %}
**What are chunks?**\
Minecraft worlds are divided into a grid of 16x16x384 cubes called chunks. Your game loads each chunk individually to piece together the world around you within your view distance.
{% endhint %}

## **Summary**

The server view distance is 14 chunks in all directions from players, making the maximum view distance in one direction 224 blocks. The server will match your personal view distance setting up to 14 to avoid sending useless world data that is outside of your render distance.\
\
**Chunks within a 3 chunk radius (48 block radius) from players are fully physically ticked**. In fully physically ticked chunks mobs will spawn, liquids will flow, redstone will function, physics apply, and all other game mechanics work as usual.

**Unlike Vanilla, fully unticked/unloaded chunks don't exist within vibe**. Growables and crops from wheat to vines will grow in unticked and even completely unloaded chunks, but at a lower tick speed than fully physically ticked chunks.\
\
**Unloaded** chunks refer to chunks that are beyond the view distance of 14 chunks. Unlike Vanilla, crops will continue to grow at a slower speed in unloaded chunks. Entities spawned when the chunk was ticking will persist within unloaded chunks with an exception of hostile entities (unless nametagged), but no entities spawn in unloaded chunks.

## Detailed configuration

### Player curated

**These rules help ensure a good balance between gameplay & latency management for players**

* The server will send up to 14 chunks in all directions to players with respect to player view distance setting, making the maximum view distance 224 blocks.
* Players chunk view distance takes priority over the servers max view distance of 14 if lower.
* The server will send no more than 65 chunks data per player per second to prevent overwhelming the connection. After testing, we found this to be the optimal threshold before it began significantly affecting latencies for many.

### Server curated

**These rules help ensure the server doesn't throttle or lag from chunks**

* Only chunks within a 3 chunk radius (48 block radius) from players are fully physically ticked and eligible for mob spawning.
* The server will load at max 65 chunks per second per player.
* The server will generate at max 65 chunks per second per player.

{% hint style="warning" %}
**Max chunk load rate is dynamic**\
Since chunks are a major lag source, especially at high activity times, the server will begin dynamically managing and lowering max chunk load rates, up to 70% to aid in keeping the server stable. The value will always bounce back to default 65 per second once the server is no longer under load or <20 players are online.
{% endhint %}

### Both

* Loaded chunks are delayed 20 seconds before unloading after they are no longer being loaded by a client. This benefits the client & server in instances where a client is teleporting between locations (ex. dying and returning) by allowing faster load times and benefits the server because it will not have to reload all the chunks again.\
