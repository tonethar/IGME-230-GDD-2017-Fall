# Week 14B - SVG part 2

## Topics
- SVG Transformations and interactions
- Hit detection

## Hit Detection
An SVG element can call getIntersectionList() to determine which of its children intersect with an argument rectangle. Any child of an SVG element (like circle, line etc.) can get its bounding box with a call to .getBBox(). The resulting array will always include the child whose boundary box is passed to getIntersectionList. The second argument to getIntersectionList specifies that only elements who have a particular ancestor will be returned. A null value for the second argument means all elements are returned regardless of ancestry.

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
  // hit list will always include circle1, as we're passing it's bounding box. It will also include any other svg elements circle1 intersects. So:
  if( hitList.length > 1 ) console.log( 'a hit!!!' );
</script>
```
[demo]

The problem with this? Firefox doesn't (yet) support getIntersectionList! So we need to do a workaround.
[demo]

## Demos
- [SVG 2 Demos](../other-files/SVG-Demos.zip)

## Exercise: Hit Detection Game
Take the [hit detection demo](), and make it so that every time the player hits the enemy, a new “blocker” shape appears at a random location. Any time the player hits a blocker, their score resets, the game ends, or something similar.

And... animate the blockers so they randomly move around, bouncing off the edges of the play area!

Place the resulting HTML file (and any external resources if needed) on Banjo and provide a link from your homepage before next class.
