# 9 - WebStorage API

## I. Overview
The HTML5 WebStorage API allows us to store key:value data in the user's browser, and that information can be retrieved at a later date by your JavaScript (when the user returns to your page).

There are some WebStorage examples on the Internet that we are going to point you to:

- https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API
- https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API
- https://html.spec.whatwg.org/multipage/webstorage.html
- https://mdn.github.io/dom-examples/web-storage/


## II. An Example

- Go ahead and try out this example, whenever you `onchange` the values of the textbox or the &lt;select>, their values are written to `localStorage`. 
- If you close the window and reopen it, your changes will be preserved.  
- After you have referred to the links above, it should be pretty easy to figure out what's going on in the code.
- One thing worth mentioning is the `prefix` variable (see below). Because Web Storage uses the same set of keys for *each domain*, this means on servers like banjo that all the students are sharing the same set of keys, so that if someone used `highscores`as a key, another student's `highscores` key could wipe out and replace the data. One solution is to prefix your key names with something unique, like your RIT web account id. Therefore `highScores` would become `abc1234highScores` for one student, and `xyz9876highScores` for someone else, and the keys would never conflict.

### webstorage-1.html
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Web Storage Example</title>
</head>
<body>

<div>
What is your name -> <input type='text' id='nameField'>
</div>

<div>
What is your favorite color -> 
<select id="colorSelect">
	<option value="red">Red</option>
	<option value="green">Green</option>
	<option value="blue">Blue</option>
	<option value="magenta">Magenta</option>
	<option value="cyan">Cyan</option>
	<option value="white">White</option>
	<option value="black">Black</option>
</select>
</div>

</body>
<script>

/* This stuff happens "onload" */
// declare some constants
const nameField = document.querySelector("#nameField");
const colorSelect = document.querySelector("#colorSelect");
const prefix = "abc1234";
const nameKey = prefix + "name"
const colorKey = prefix + "color";

// grab the stored data, will get null if user has never been to this page
const storedName = localStorage.getItem(nameKey);
const storedColor = localStorage.getItem(colorKey);

// if we find a previously set name value, display it
if (storedName){
	nameField.value = storedName;
}else{
	nameField.value = "Turbo";
}

// if we find a previously set color value, display it
if (storedColor){
	colorSelect.querySelector(`option[value='${storedColor}']`).selected = true;
}

/* This stuff happens later when the user does something */
// when the user changes their favorites, update localStorage
nameField.onchange = e=>{ localStorage.setItem(nameKey, e.target.value); };
colorSelect.onchange = e=>{ localStorage.setItem(colorKey, e.target.value); };


</script>
</html>
```

### A. And here is what it looks like:

![Web Page](_images/web-storage-1.jpg)


## III. Review Questions
1. What is difference between local and session storage?
1. If the user opens up the demo page in a different web browser, will their answers still be visible? Why or why not?

<hr>

**[Previous Section <- JavaScript Arrays (part 8)](web-apps-8.md)**

**[Next Section -> Web Services (part 10)](web-apps-10.md)**
