# Protecting the community

The server has numerous systems in place to prevent bad actors & disruptive behavior to ensure everybody has a safe and enjoyable experience. This page outlines the precautions we take to protect players :)\


**Traffic filtration**\
All server bound traffic is proxied and examined before being passed to the backend or dropped. This allows us to manage traffic flow to the backend and significantly mitigate malicious traffic before it can impact the server. Using Cloudflare Magic Transit, our network is guarded by over 1+ Tbps of L3/L4 DDoS protection.\


**Movement analysis**\
We use a machine learning anticheat equip with a full replication of player's possible movements and the ability to take into account how players interact in their unique environment, preventing virtually any illegitimate action while maintaining extremely low false positive rates.

\
**Block data obfuscation based anti x-ray**\
This system sends a mixture of air and fake ore block data in replacement of all solid blocks underground. As players mine, the fake ore data is replaced by the real block data within a radius of the player. With decent latency, this system is invisible to legitimate players, however high latency connections may see the fake ores for a moment before the the real block data arrives and updates on the client.\


**Mining pattern examination anti x-ray**\
While block data obfuscation is typically enough to prevent most cheaters, in some circumstances the obfuscation can be bypassed by sophisticated means. To combat this, we use intelligent algorithms to examine mining patterns and punish players if they're found to be behaving illegitimately.

\
**Exploit prevention**\
Game breaking exploits are patched on the server to ensure everybody plays fair.\
\
Notable exploits we've patched include but are not limited to:

* Swamp clay patch diamonds
* TNT duplicators
* Piston duplication
* Invulnerable end crystals
* GUI/packet based item duplication\


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
Analysis of behavior & patterns allows the server to preemptively identify and mitigate bot attacks. In the unlikely event our layer 7 filtration fails and worst comes to worst, the server is capable of locking down and only allowing previously identified players to connect to ensure uninterrupted access for legitimate players.

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
As a last resort or if data becomes permanently corrupt, damaged, or otherwise lost we can selectively restore data from the applicable backup. The entire server filesystem is incrementally backed up every 12h, allowing full access of all recent or old server data.

Additionally, smaller selective hot player data is backed up and stored on the server on session start and end, world change, and death. The server will hold up to 100 backups in each action category per player before it begins rotating them, making the maximum backups held per player 400. Each backup stores a snapshot of the players location, inventory, enderchest, balance, experience, and other metrics.\
\
\
**Account linking**\
To access our Discord and view any channels, users must first verify their Discord account through the mc server via a simple automated process to ensure only server members can access the Discord. Not only does this cultivate a more exclusive, close-knit community space because everybody is able to recognize people by the same usernames, but this also provides the server the ability to automatically synchronize display name/nickname changes, ranks, mutes & bans, and more across the MC server and Discord server. &#x20;
