# HW - Circle Blast! - Part 3

## I. Overview
In this walkthrough we will complete *Circle Blast!*.



## II. Shooting Bullets
So the player can die by deliberately running into the circles, but can't actually harm the circles without running into them. That's not too interesting, so let's get shooting working.

### II-A. The `Bullet` class

- **Add the following to classes.js:**




## X. Possible improvements
- imported font
- imported graphics, and only use PIXI.Text for "dynamic text" that changes (e.g. score)
- sounds
  - background music
  - "lose scene" sound
- enemies also explode when they collide with the ship (but use a different, smaller explosion)
- more enemy types
	- enemies that "wrap" instead of bounce off the sides of the scene
    - more interesting movement
    - enemies that dodge bullets
    - kamikaze enemies
    - enemies that shoot bullets or fire guided missiles
    - more than one hit to kill
- more weapons
- power ups: shields, heal, double fire, faster fire
- when the ship is hit, it gets temporary invulnerability before it can be damaged again
- a story
- something to protect:
    - space caravans of colonists
    - cities
    - space stations
    - asteroid miners
- keyboard control
    - spacebar to fire 
- Coding
    - create a reusable `Button` class
    - create a reusable `Explosion` class
    
<hr>
<hr>

**[Previous Chapter <- Circle Blast! (part 2)](HW-circle-blast-2.md)**
