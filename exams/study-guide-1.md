# Study Guide #1

## 1. Basic HTML Selectors
You should already know most of this from IGME-110.

Imagine you have the following HTML:

```
<ol id='listDaily' class='myLists'>
  <li>Wake Up</li>
  <li>Get out of Bed</li>
  <li>Eat Breakfast</li>
  <li>Bathe & Brush Teeth</li>
  <li>Get Dressed</li>
  <li>Go to School</li>
</ol>

<ul id='listShopping' class='myLists'>
  <li>Eggs</li>
  <li>Apples</li>
  <li>Bread</li>
  <li>Milk</li>
</ul>

<ol id='nixonEnemies'>
  <li>Arnold Picker</li>
  <li>Alexander E. Barkan</li>
  <li>Edwin Guthman</li>
  <li>Maxwell Dane</li>
  <li>Charles Dyson</li>
</ol>
```

A) Write a CSS rule that selects both of the ordered lists above and sets their `font-size` to `20px` (hint: use a *type selector*).

We'll do this one for you:
```
ol{ font-size: 20px; }

```

B) Write a CSS rule that selects the shopping list and sets the `font-size` to `24px` - use a *type selector*.

C) Write a CSS rule that selects the shopping list and sets the `color` to `red` - but this time use an *id selector*.

D) Write a CSS rule that selects the lists that are of the class "myLists" above and set the `background-color` to `yellow` - use a *class selector*.

E) Write a CSS rule that selects each of the list-items in all three lists and sets their `font-weight` to `bold` - use the *universal (or wildcard) selector*.

## 2. CSS3 Selectors
CSS3 Selectors are supported by all modern browsers.
