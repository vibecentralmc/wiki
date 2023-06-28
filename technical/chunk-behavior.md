# Chunk behavior

Chunk behavior has been heavily modified to accommodate multiplayer. Our modifications aim to achieve a balance between minimizing latency lag, providing a good gameplay experience, and being computationally capable for the server.

{% hint style="info" %}
**What are chunks?**\
Minecraft worlds are divided into a grid of 16x16x320 cubes called chunks. Your game loads each chunk individually to piece together the world around you within your view distance.
{% endhint %}

## **Summary**

The server view distance is 15 chunks in all directions from players, making the maximum view distance of 480 blocks. Note that in order to prevent useless traffic this will match your personal view distance setting up to 15, so if your view distance is for example 8, you will only be sent chunk data for a view distance of 8.\
\
**Chunks within a 2 chunk radius (32 blocks in all directions) from players are fully physically ticked**. In fully physically ticked chunks, liquids will flow, redstone will function, physics apply, and all other game mechanics work as usual.

**Unlike Vanilla, fully unticked/unloaded chunks don't exist within vibe**. Mobs can spawn and interact with unticked chunks around the player as they use a [totally separate ticking system](entity-de-spawning-and-ai.md). Additionally, all growables and crops from wheat to vines will grow in unticked and even completely unloaded chunks, but at a lower tick speed than fully physically ticked chunks.\
\
**Unloaded** chunks refer to chunks that are beyond the view distance of 15 chunks. Unlike Vanilla, crops will continue to grow at a slower speed in unloaded chunks. Entities spawned when the chunk was ticked will persist within unloaded chunks with an exception of hostile entities (unless nametagged), but no entities spawn in unloaded chunks.

## Detailed configuration

### Player curated

**These rules help ensure a good balance between gameplay & latency management for players**

* The server will send up to 15 chunks in all directions to players with respect to player view distance setting, making the maximum view distance of 480 blocks. However, only a 2 chunk radius (32 block radius) is fully physically ticked.
* Players chunk view distance takes priority over the servers max view distance of 15 if lower.
* To minimize the time appearing in a void, chunk data in a 2 chunk radius around players are immediately sent without throttling after teleporting.
* The server will send no more than 45 chunks data per player per second to prevent overwhelming the connection. After testing, we found this to be the optimal threshold before it began significantly affecting latencies for many.

### Server curated

**These rules help ensure the server doesn't throttle or lag from chunks**

* Chunks within a 2 chunk radius (32 blocks in all directions) from players are fully physically ticked. In fully ticked chunks, liquids will flow, redstone will function, physics apply, and all other game mechanics work as usual. Unlike Vanilla, fully unticked/unloaded chunks don't exist within vibe, as mobs can spawn and interact with unticked chunks around the player as they use a [totally separate ticking system](entity-de-spawning-and-ai.md). Additionally, all growables and crops from nether warts to potatoes will tick in unticked and even completely unloaded chunks, but at a lower rate than ticked chunks. &#x20;
* The server will load at max 45 chunks per second per player.
* The server will load at max 500 chunks per second (combined amount from all players).
* Only chunks in a 2 chunk radius (32 blocks in all directions) from the client are ticked. Chunks beyond this radius may be visible, but are not physically ticked.

### Both

* Loaded chunks are delayed 15 seconds before unloading after they are no longer being loaded by a client. This benefits the client & server in instances where a client is teleporting between locations (ex. dying and returning) by allowing faster load times and benefits the server because it will not have to reload all the chunks again.\
