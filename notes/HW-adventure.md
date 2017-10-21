# Adventure! Game

## I. This is currently a demo (all done for you), not a homework assignment. You can download the complete files here:

[HW-adventure-done.zip](_files/HW-adventure-done.zip)

This game could be a good start on project 2 - either as a turn-based Rogue-like (the monsters move when the player does), or with real-time challenges (see the [HW-Life.md](HW-life.md) exercise to see how to set up a game loop using `window.requestAnimationFrame()`

### A. Screen shot of final version:
![Web Page](images/adventure-1.jpg)

## II. Features
1. Game board is laid out on a 30x20 grid.
    - map is read from a 2D array in `gameworld.js`.
    - Tile types are floor, wall, grass, water and ground. 
    - Tile backgrounds are CSS image sprites read from terrain.png as CSS image sprites - see  [HW-chibi-matching.md](./HW-chibi-matching.md) for an explanation.
1. Player can use arrow keys to move their `player` avatar up, down, left, and right `onmousedown`
    - uses CSS animations - `transition-property: all;` and `transition-duration: .2s;` for a smooth transition between tiles.
    - not allowed to move into wall or water squares - see the `checkIsLegalMove(nextX,nextY)` function.
    - the `gameObjects` array is looped through every time the player moves, and the objects and monsters are re-positioned if necessary.
1. A simple audio effect using a hidden &lt;audio> tag - it is played when the player attempts to enter a wall or water square.
1. An array - (but not a 2D array) is used to hold "Game Objects" like the treasure chest, key, and monsters. This allows there to be more than one "game object" per square, and it makes it easy to move them.
1. The code for detecting which square is clicked by the mouse is implemented, but not used
1. If you don't like the border between the tiles, set `cellSpacing = 0`, and in the CSS under `span.cell` set `border:none;`

## III.Possible Enhancements
- Use ES6 classes for the GameObjects (monsters, treasures, keys).
- get the monsters to move, either turn-based or real-time
- handle player:monster and player:game object collisions
- give the player a HUD for hitpoints, items, level etc
- have multiple levels
- add story elements
- or do a completely different kind of a game like [Robots aka Daleks](https://en.wikipedia.org/wiki/Robots_(computer_game))
