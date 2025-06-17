# Tak
Minimalist UI for local play in a single HTML file. Just Open with a browser and play.

## UI
Choose a board size (from 3 to 8) and press **New Game** to start.

Choose a custom color scheme. (Automatically rerendered and saved. Resetting to defaults returns to original colors, not previously saved colors.)

Toggle player controls using number keys
1. Hand: pick up and move pieces/stacks.
   - Click to pick up: removes all the stones you can carry from the top of that stack and puts them in your hand.
   - Click to place: drops a stone from the bottom of your picked up stack on top of that square.
2. Square: place flat/standing stones (select again to toggle)
3. Circle: place capstones

Keyboard Shortcuts
- Undo: z
- Redo: v
- Settings: s
- New Game: n
- History: h

Click a line in the game history to jump to that board state.

## Other Details
All pieces are displayed 2D (flats as rectangles, standing as triangles, caps as circles). 

Current player has black outline on controls.

Stacks are drawn in column major order (starting from top left, going down the column, then continuing down the next column to the right). This prevents stacks from occluding each other, but means the pieces can get small on big boards with tall stacks.

Each column is the height of the carry limit, and the leftmost column is twice as wide as the others (representing the most stones you can grab).

[TPS](https://ustak.org/tak-positional-system-tps/) is used to store history, rather than [PTN](https://ustak.org/portable-tak-notation/). TPS is more verbose, human readable, and puzzle friendly, imo.

Maximum number of flat+standing stones and capstones set according to the [US Tak Association](https://ustak.org/play-beautiful-game-tak/), but the js can be edited for custom piece limits.

`const stoneMax = {3:10,4:15,5:21,6:30,7:40,8:50}`

`const capMax = {3:0,4:0,5:1,6:1,7:2,8:2}`
