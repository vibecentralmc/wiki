# Entity (de)spawning and AI

As entities are one of the biggest server lag sources for multiplayer, the spawning rules have been heavily modified to accommodate for multiplayer. Our modifications aim to achieve a balance between providing a familiar experience and being computationally capable for the server.

## Tracking range

Entities are only viewable to players while they're within a specific range of them. This is called their tracking range. Tracking range is entirely clientside, and helps reduce latency and improve FPS by only rendering entities that are closeby.\
\
Players: 145 blocks\
Hostiles: 85 blocks\
Animals: 85 blocks\
Misc: 42 blocks

## Spawning

Per dimension, within [physically ticked chunks](chunk-behavior.md) (3 chunk radius or 48 blocks in all directions around players) the server will spawn no more than a certain number of entities of particular types. Chunks are consistently being loaded & unloaded, meaning the cap for how many of these entities can spawn is constantly shifting. The total amount of entities spawned & observed in the world is much higher than these caps (this is what observed entities refers to). Entities spawned when the [chunk was ticking](chunk-behavior.md) will persist within unticked chunks with an exception of hostile entities at a certain distance unless nametagged (see [despawning ](entity-de-spawning-and-ai.md#despawning)section). No entities spawn in [unloaded chunks](chunk-behavior.md).

Entities are spawned spread amongst all players until their cap is reached. This means at peak activity times, you'll notice less entities around you as they're more spread out. Already existing entities around players are taken into account before spawning new ones. The server will favor spawning entities near players which are not around specific entity groups and are in spaces which meet those entities' spawning requirements over other players who are already around those entity types. This enables a more singleplayer-like and balanced spawning experience while keeping resource use reasonable.\
\
Spawn rate refers to how frequently the server checks conditions around players as well as computes which applicable player the mob should spawn near. An entity is not always successfully spawned every spawn rate, for example when the cap is reached or there are no locations near players meeting the spawn requirements.\
\
Consistent with Vanilla behavior, mobs will not spawn within a 24 block radius of players. With the other settings, this means auto farms cannot exceed a radius of 32 blocks for spawning. This makes the ideal AFK position just under 48 blocks away from the spawning zone (either above or below) vertically.\


**Hostiles**\
Observed entities (avg): 300-800\
Spawn rate: 0.5 seconds

**Animals**\
Observed entities (avg): 50-200\
Spawn rate: 20 seconds

**Axolotls**\
Observed entities (avg): 10-40\
Spawn rate: 20 seconds\
\
**Sea creatures**\
Observed entities (avg): 20-90\
Spawn rate: 20 seconds

## Despawning

### **Range-based despawning**

**Hostiles & sea creatures**\
Chance to despawn when: >28 blocks\
Immediately despawned when: >48 blocks horizontally, and >128 blocks vertically&#x20;

### **Radius-based (mob cap) despawning**

{% hint style="info" %}
**Good to know**\


* Nametagged and tamed mobs are exempt from despawning\

* Overflow mobs are checked and despawned once every 65 seconds, meaning you can have mobs exceeding the limits temporarily but they will be at risk of being removed\

* Radius is calculated from each mobs position, meaning you'll want to have a gap of at least the radius starting from the outermost mob
{% endhint %}

**Animals (pig, cow, sheep, chicken)**\
Main cap: 22\
Within: 14x14 blocks\
\
Secondary cap: 10\
Within 2x2 blocks\
\
**Rabbits**\
Cap: 12\
Within: 15x15 blocks\
\
**Bees**\
Cap: 12\
Within: 8x8 blocks\
\
**Villagers**\
Cap: 8\
Within: 6x6 blocks\
\
**Iron Golems**\
Cap: 8\
Within: 15x15 blocks\
\
**Turtles**\
Cap: 8\
Within: 7x7 blocks\
\
**Frogs**\
Cap: 20\
Within: 15x15 blocks\
\
**Pandas**\
Cap: 8\
Within: 15x15 blocks\
\
**Armor Stands**\
Cap: 35\
Within: 6x6 blocks\
\
**Paintings**\
Cap: 10\
Within: 10x10 blocks\
\
**Ender Crystals**\
Cap: 5\
Within: 6x6 blocks\
\
**Boats**\
Cap: 6\
Within: 15x15 blocks\
\
**Minecarts**\
Cap: 8\
Within: 13x13 blocks\
\
**Item Frames**\
Cap: 120\
Within: 15x15 blocks\
Exclusive to creative plots & the parkour course builder

### **Additional**

These entities are despawned by range-based and radius-based despawning to fine tune their spawning behavior

<details>

<summary>Expand</summary>

**Zombified Piglins**\
Cap: 12\
Within: 15x15 blocks\
Exclusive to nether\
\
**Striders**\
Cap: 6\
Within: 16x16 blocks\
Exclusive to nether\
\
**Dolphins**\
Cap: 6\
Within: 32x32 blocks\
\
**Squids**\
Cap: 10\
Within: 25x25 blocks\
\
**Drowned**\
Cap: 6\
Within: 42x42 blocks\
\
**Guardians**\
Cap: 8\
Within: 10x10 blocks\
\
**Cod + Salmon**\
Cap: 25\
Within: 10x10 blocks\
\
**Tropical Fish**\
Cap: 17\
Within: 10x10 blocks\
\
**Pillagers**\
Cap: 8\
Within: 4x4 blocks\
\
**Axolotls**\
Cap: 20\
Within: 15x15 blocks\
\
**All entities (unless overridden by another cap)**\
Cap: 5\
Within: 6x6 blocks\
Exclusive to creative plots & the parkour course builder

</details>

### Lifetime-based despawning

Arrows: 25 seconds\
Creative arrows: 10 seconds\
Tridents: 1 minute\
Items: 3 minutes (select super common items despawn faster for server performance, see below)

<details>

<summary>Alternate item despawn times</summary>

If an item is not listed, it uses the regular 3 min despawn time.

#### **5 seconds**

* Stick

***

#### **10 seconds**

* Acacia Leaves
* Arrow
* Azalea Leaves
* Birch Leaves
* Bone
* Cobblestone
* Dark Oak Leaves
* Dirt
* Gravel
* Gunpowder
* Jungle Leaves
* Kelp
* Mangrove Leaves
* Oak Leaves
* Rotten Flesh
* Spider Eye
* Spruce Leaves
* String

***

#### **15 seconds**

* Andesite
* Bamboo
* Cactus
* Diorite
* Granite
* Red Sand
* Sand
* Sugar Cane
* Twisting Vines
* Weeping Vines

***

#### **30 seconds**

* Scaffolding

***

#### **40 seconds**

* Melon Slice
* Pumpkin

</details>

{% hint style="info" %}
A tick refers to the game loop firing. Without lag, the game runs at 20 ticks per second, updating entity AI, block changes, and everything else in the game.
{% endhint %}

## Entity AI

Entities AI allow them to interact with their surroundings, whether by moving, reacting to damage, or other events. Only entities which are close enough to players retain their AI. The server uses two main algorithms for determining an entity's AI: EAR (entity activation range) & DAB (dynamic activation of brain).\
\
EAR works by fully activating entity AI if they are within a defined radius of players. DAB takes this a step further and reduces the amount an entity is ticked the further away it is from players. It works on a gradient instead of a hard cutoff like EAR; instead of fully ticking close entities and barely ticking far entities like EAR, DAB reduces the frequency an entity is ticked (lessens their AI) based on the exact distance they are from players. DAB provides major optimization to entities performance hit without being very noticeable, and allows the server to spawn more mobs at the cost of reducing the AI or activity of mobs further away from players.\
\
In mob farms congested with entities, additional one-off algorithms selectively disable & re-enable random pathfinding movement, collisions, and in some cases entirety of AI, even when within EAR range.

### EAR ranges

Hostiles: 24 blocks\
Animals: 14 blocks\
Villagers: 14 blocks\
Raiders: 48 blocks\
Water creatures: 32 blocks\
Misc. entities: 8 blocks

### DAB

Begins ticking less frequently on a gradient when: >8 blocks away\
Slowest tick frequency: every 60 ticks when at a distance of 20 or more blocks away\
\
Ghast, Slime, and Endermen are exempt from DAB.\


{% hint style="info" %}
When AI is fully activated, entities are ticked every single tick (20 times / sec).
{% endhint %}
