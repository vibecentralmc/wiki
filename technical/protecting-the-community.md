# Protecting the community

The server has numerous systems in place to prevent bad actors & disruptive behavior to ensure everybody has a safe and enjoyable experience. This page outlines the precautions we take to protect players :)\


**Movement analysis**\
We utilize a sophisticated machine learning anticheat that runs 1:1 simulations of legitimate movements on all players. By comparing the simulation to the input from your client, the game can catch and prevent cheating with extremely high accuracy.

\
**Block data obfuscation based anti x-ray**\
X-Ray is one of the biggest cheats utilized in public smps, and is extremely easy to use with just a resource pack. We combat this by tampering with the block data sent to players clients from the server in real time. While underground, the server tells your client that all solid blocks that should be out of your vision are a mixture of air and ore blocks. As players mine, the fake world data is replaced by the real block data if it should be legitimately visible to the player. The result eliminates the effectiveness of x-ray drastically because there's no way to tell which ores are real or fake until you are directly in front of them or mine them. With decent latency, this system is invisible to legitimate players, however high latency connections may see the fake ores for a moment before the the real block data arrives and updates on the client.\


**Mining pattern examination anti x-ray**\
While block data obfuscation is nearly always enough to prevent cheaters, reverse engineering seeds is something that is possible under rare circumstances which can render the obfuscation useless. To combat this, we utilize systems trained on historical legitimate behavior from the server that examine mining patterns and alert staff of any suspicious behavior for investigation. In vibe's history, there has been no known instances of seeds being reverse engineered. Paper servers also take extra measures to protect seed integrity by default, by using a variety of different seeds for different terrain features & structures.

\
**Exploit prevention**\
Game breaking exploits are patched on the server to ensure everybody plays fair.\
\
Notable exploits we've patched include but are not limited to:

* Swamp clay patch diamonds
* TNT duplicators
* Piston duplication
* Invulnerable end crystals
* GUI/packet based item duplication
* Lava pool debris\


**Packet analysis**\
Incoming packets from clients are cross verified to ensure the server can safely accept them. Additionally, the server will drop legitimate packets received from clients if they exceed 700 within a 5 second period.

Typically unmodified clients avg. \~2-50pps, but this value can reach up to around \~160pps depending on activity. For this reason, a rate of 160 or more pps for over 5 seconds is considered malicious by the server.

\
**In depth activity logging**\
Virtually all user interactions with the server and its features are saved even down to niche actions to allow a full recreation of events, making any damages easily reversable. If needed, staff can view user history and selectively roll back events, making any sort of griefing/robbery, feature exploitation, or other misconduct incredibly easy to handle. This allows us to never have to guess when investigating user issues and is also what allows us to offer our no-grief guarantee to players.

\
**Content filtration**\
We have various filters spanning chat, signs, books, and anvils to prevent misconduct. Through deep analysis of players messages, the server is capable of intelligently recognizing and preventing chat misconduct, including but not limited to spam-like content & repeated message spam, disallowed sites, disallowed language or characters, chat flooding, and more.\
\
\
**Bot prevention**\
Analysis of auth, join, and chat behavior protects the server with preemptive identification and mitigation of bot attacks. In the unlikely event our layer 7 filtration fails and worst comes to worst, the server is capable of locking down and only allowing previously identified players to connect, ensuring uninterrupted access for legitimate players.

\
**Real-time staff alerts**\
The server will automatically alert staff via Discord with warnings regarding server performance drops, auto mutes/bans, and other notifications to ensure the server is monitored around the clock. This system allows us to act as quickly as possible if anything urgent requiring staffs attention happens.\
\
Players may also use our ticket function on Discord to privately contact staff with any concerns or to reach out for help.

\
**NBT filtration**\
For players in creative mode, NBT data is filtered and sometimes stripped on a packet level from items they add to their inventory whether via saved hotbar, client, or by other means. This ensures no bad NBT can impact the server or players.

\
**Redstone rate limiting**\
Player's redstone is rate limited to prevent users building lag machines. By keeping track of who placed what redstone and the rate at which their combined redstone is pulsing, the redstone will be destroyed and if the incident is severe enough and suspected as a lag machine, the player will be automatically banned.

\
**Backups**\
As a last resort or if data becomes permanently corrupt, damaged, or otherwise lost we can selectively restore data from the applicable backup. The entire server filesystem is incrementally backed up regularly, allowing full access of all recent or old server data.

Additionally, smaller selective hot player data is backed up and stored on the server on session start and end, world change, and death. The server will hold up to 100 backups in each action category per player before it begins rotating them, making the maximum backups held per player 400. Each backup stores a snapshot of the players location, inventory, enderchest, balance, experience, and other metrics.\
\
\
**Account linking**\
To access our Discord and view any channels, users must first verify their Discord account through the mc server via a simple automated process to ensure only server members can access the Discord. Not only does this cultivate a more close knit community space because everybody is able to recognize people by the same usernames, but it also provides us the ability to automatically synchronize display name/nickname changes, ranks, mutes & bans, and more across the MC server and Discord server. &#x20;
