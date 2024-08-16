# WorldEdit

WorldEdit is a popular building tool developed by sk89q. It allows players the ability to mass edit large quantities of blocks through commands to assist in creative building.&#x20;

We offer a more user friendly version of WorldEdit available in [creative plots](../../creative-plots/creative-plots.md) & the [parkour builder](../../parkour/parkour.md) to help you speed up your building. Advanced WE features like brushes are not available to encourage more unique, carefully composed handmade builds. With the abilities available, we hope to reduce annoying grunt work such as filling big areas with the same block, clearing out large amounts of blocks, and so forth.

Operations are primarily applied on cuboid selections. Selections are visualized with purple particles, and other players' selections are visualized with orange flame particles. You can only create one selection at a time.

A single operation can change up to 500,000 blocks or 500 tiles.

### Creating a selection

WE selection creation is very much the same as survival [land claiming](../../survival/land-claiming.md) selections, however with WorldEdit, Y axis (up and down) is taken into account. To create a cuboid selection, use the 'wand' tool - a golden axe. While holding the axe, right-click the block you'd like for your first corner, and then left-click in the opposite corner to create a cuboid selection. If done correctly, the selection will be visualized with purple particles (make sure you have particles enabled in your games settings). This cube represents the blocks that will be affected by operations. See the commands below to see how to execute various operations.

Unlike vanilla WorldEdit, operations on vibe are performed asynchronously and thus unmetered, meaning you can change as many blocks as you'd like in a single operation. The server will complete operations as fast as it can without impacting its performance, which is typically pretty quick unless the server is under substantial load due to player count or other factors. Do note that very large operations may take some extra time. If an operation cannot be executed immediately, a progress bar will be shown at the top of your screen.

### Commands

* **`//wand`**\
  Allows you to select two positions to create a cuboid selection. Use //set or another WorldEdit command to modify the space in between the two positions. The cuboid is visualized with purple particles, and other players' cuboids are visualized with orange flame particles.\

* **`//set <block,block,block,etc>`**\
  Sets your WorldEdit selection to a target block or mix of blocks\

* **`//replace <target block(s)> <with block(s)>`**\
  Replaces target blocks within your selection with new blocks\

* **`//fixwater <radius>`**\
  **`//fixlava <radius>`**\
  Turns the body of liquid you're in (within the radius) to source blocks\

* **`//drain <radius>`**\
  Drain water/lava in a body of liquid within the specified radius of you. You must be in the target body of liquid\

* **`//gmask <block(s)>`**\
  Sets a global mask for your WorldEdit operations. When a global mask is active, all other blocks not included in the mask will be ignored\

* **`//deselect`**\
  **`//desel`**\
  Deselects your current WorldEdit selection\

* **`//undo`**\
  Undoes your last WorldEdit operation\

* **`//copy`**\
  **`//paste`**\
  Copy your current selection or paste your chipboard relative to your copy position\

* **`//rotate <deg>`**\
  Rotate your clipboard\

* **`//flip [direction]`**\
  Flip your clipboard the specified direction, or if no direction is specified, the direction you are currently facing\

* **`/up <num>`**\
  Teleport up x amount of blocks and place a platform under you
