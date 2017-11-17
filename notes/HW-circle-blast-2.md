# HW - Circle Blast! - Part 2

## I. Overview
In this walkthrough we will complete *Circle Blast!*.

## II. Implement our main "game loop"

We are going to skip past "#7 - load sprite sheet" for now and instead handle "#8 - Start update loop"

### IIA. Get started on `gameLoop()`
Here's the stub for `gameLoop()`, in copy/paste form. Add this to the bottom of **main.js**:


```
function gameLoop(){
	// if (paused) return; // keep this commented out for now
	
	// #1 - Calculate "delta time"
	
	
	// #2 - Move Ship
	
	
	// #3 - Move Circles
	
	
	// #4 - Move Bullets

	
	// #5 - Check for Collisions
	
	
	// #6 - Now do some clean up
	
	
	// #7 - Is game over?
	
	
	// #8 - Load next level
}
```

- **And now we need to call it, 60 times a second. Add the following to the `setup()` function:**

```javascript
// #8 - Start update loop
app.ticker.add(gameLoop);
```

### IIB. Calculate "Delta time"

We need to figure out how much time has passed since the last update, and adjust the speed of our sprites accordingly.
Ideally, this would be precisely 1/60th of a second, but frame rates can fluctuate depending on what else the browser or OS is working on, so calculating this value every frame makes the animations run much smoother. 

- **Add the following to `gameLoop()`:**

```javascript
// #1 - Calculate "delta time"
let dt = 1/app.ticker.FPS;
if (dt > 1/12) dt=1/12;
```

Note that if `dt` is greater than 1/12 of a second we will clamp it to 1/12 of a second. When could `dt` be that large? #1 - When first starting the game up, and #2 - when the user creates a new browser tab in the same window as the game, `app.ticker` will pause the updates. If the user returns 5 seconds later, `dt` will now be 5 instead of 1/60, which will wreck the game animation.


### IIC. Get the ship moving

- **Add the following to `gameLoop()`:**

```javascript
// #2 - Move Ship
let mousePosition = app.renderer.plugins.interaction.mouse.global;
ship.position = mousePosition;
	
```

Note: `.position` is a [PIXI.Point](http://pixijs.download/dev/docs/PIXI.Point.html) - which is an object that looks like this `{x:0,y:0}`

Reload the page and try it out. The ship should now move to the position of the mouse pointer (which gives it an unreasonably fast speed). The ship will also move off of the game scene, which is not good.

- **Modify the code to instead look like this**

![Screenshot](_images/circle-blast-15.jpg)

The ship should now smoothly move towards the position of the mouse. If you would rather have a slower or faster ship, you just have to tweak `amt`.

Note: Here we are using the `lerp()` and `clamp()` helper functions that were give to you in **utilities.js** - please check out the implementaion of those functions right now.


## III. Create some obstacles

So we have a moving ship, but no opponents yet. Now we need to create those circles that the player will eventually be dodging and shooting.

### IIIA. Create the Circle class.

- **Add the following to classes.js:**

![Screenshot](_images/circle-blast-16.jpg)

Note that this is an improved version of the `Circle` we created back in [Pixi 2 - ES6 Classes & PixiJS Animation](pixi-js-2.md):
- we are now using `dt` so that the circle's perceived speed never changes, regardless of what the actual frame rate of the game is.
- we are using the `getRandomUnitVector()` function (defined in **utilities.js**) so that `fwd` is always a *unit vector* (displacement of 1), which means that all of our circles are going to move at the same speed.

- **Reload the page - there should not be any errors**

### IIIB. Implement the `createCircles()` function.

**Here's a new function for main.js - it needs to look like this:**

![Screenshot](_images/circle-blast-17.jpg)

This code is hopefully self-explanatory: it creates circles, adds them to the array, and places them on the top 1/3 of the scene (plus a 25-pixel margin).

- **Test the code by typing this into the console -  `createCircles(100)` - which should create 100 circles and put them on the screen:**

![Screenshot](_images/circle-blast-18.jpg)


## IV. Get level loading working

### IVA. In **main.js** implement `loadLevel()`:

```
function loadLevel(){
	createCircles(levelNum * 5);
	paused = false;
}
```

### IVB. Now make `startGame()` look like this:

![Screenshot](_images/circle-blast-19.jpg)

- **Reload the page - click the start button - there should be 5 circles at the top of the screen**

### IVC. Get the circles moving

- **Finally, to get the circles moving, add the following to `gameLoop()`:**

![Screenshot](_images/circle-blast-20.jpg)

- **and be sure to *uncomment* this line of code that is at the top `gameLoop()`:**

 `if (paused) return;`
 
- **Reload the page - the 5 circles are now moving and bouncing off of the sides of the scene**


## V. Checking for Ship->Circle Collisions



## X. Possible improvements
- imported font
- imported graphics, and only use PIXI.Text for "dynamic text" that changes (e.g. score)
- sounds
  - background music
  - "lose scene" sound
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


 **[Previous Chapter <- Circle Blast! (part 1)](HW-circle-blast.md)**
