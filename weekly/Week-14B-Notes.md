# Week 14B - SVG part 2

## Topics
- SVG Transformations and interactions
- Hit detection

## Transformations
SVG objects can be transformed using the same CSS properties you may have see before. We can animate these transformations via ```requestAnimationFrame()``` and we can also determine factors such as the point around which a transformation takes place.

(see demo 1)

## Interactions with SVG
These demos review how to add, remove, and animate SVG objects, and how we can add some interactivity. The first one is a timed clicking game, and the second is a very simple mouse-following example.

(see demo 2 and 3)

## Hit Detection
An SVG element can call ```getIntersectionList()``` to determine which of its children intersect with an argument rectangle. Any child of an SVG element (like circle, line etc.) can get its bounding box with a call to ```.getBBox()```. The resulting array will always include the child whose boundary box is passed to ```getIntersectionList()```. The second argument to ```getIntersectionList()``` specifies that only elements who have a particular ancestor will be returned. A null value for the second argument means all elements are returned regardless of ancestry.

```html
<body>
  <svg>
  <circle />
  <circle />
  <circle />
  </svg>
</body>
<script>
  let mysvg = document.querySelector( 'svg' );
  let circle1 = mysvg.children[ 0 ];
  // get circle1 boundary box, not beat box
  let bbox = circle1.getBBox();
  // check to see if circle1 intersects any of the other circles
  let hitList = svg.getIntersectionList( bbox, null );
  // hit list will always include circle1, as we're passing its bounding box. 
  // It will also include any other svg elements circle1 intersects. So:
  if( hitList.length > 1 ) console.log( 'a hit!!!' );
</script>
```
(see demo 4)

The problem with this? Firefox doesn't (yet) support getIntersectionList! So we need to do a workaround; see demo 5.

## Demos
- [SVG 2 Demos](../other-files/SVG-2-Demos.zip)

## Cool Student Examples
- Multiplayer tank battle game: http://nerdnuke.net:3000/
- Stack: https://people.rit.edu/~nac5961/230/project3/index.html
- [D3](https://d3js.org/) audio visualizer: https://people.rit.edu/~cmg7063/230/project3/index.html
- Fireworks: https://people.rit.edu/~imm3350/230/project3/index.html

## More Resources
- Great coverage of the different SVG elements - http://tutorials.jenkov.com/svg/index.html
- More details on how getIntersectionList works - https://www.w3.org/TR/SVG/struct.html#__svg__SVGSVGElement__getIntersectionList
- Animating SVG without JavaScript - https://css-tricks.com/guide-svg-animations-smil/

## Exercise: Hit Detection Game
Take demo 4, and make it so that every time the player hits the enemy, a new “blocker” shape appears at a random location (3 points).
Any time the player hits a blocker, their score resets, the game ends, or something similar (7 points).

For a bonus 5 points, animate the blockers so they randomly move around, bouncing off the edges of the play area!

Place the resulting HTML file (and any external resources if needed) on Banjo and provide a link from your homepage before next week's first class.

## Review Questions
1. How often is ```requestAnimationFrame``` called?
1. What does ```getIntersectionList``` do?
1. What does ```getBBox()``` return?
