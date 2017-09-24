# More Web Browser DOM Methods

## I. Overview
Today we are going to look at other ways to use JavaScript to alter HTML elements on the page. 
Although we can do quite a bit with the `.innerHTML` property, there are times that we might want to insert a new element somewhere on the page, for example a new list item into the middle of a list. Or to delete a single element, for example a list item that is currently inside (a child of) an unordered list. To do these things, we are going to need more fine grained control.

### A. The DOM is an inverted tree
The browser DOM is an inverted tree structure that consists of *nodes* mostly HTML elements that are software *objects* that have properties and methods associated with them.. These nodes have hierarchical relationships with one another - *parent*, *child*, and *sibling*.  Read about this here: https://www.w3schools.com/js/js_htmldom_navigation.asp

Today we will learn how to create new DOM elements and insert them anywhere into the DOM tree that we want to.

![Web Page](_images/more-dom-0.jpg)

### B. New DOM Methods
Here are some of the new DOM methods we will be working with today:

- `document.createElement(elementName)` -- https://developer.mozilla.org/en-US/docs/Web/API/Document/createElement
- `document.createTextNode(text)` -- https://developer.mozilla.org/en-US/docs/Web/API/Document/createTextNode
- `element.getAttribute(attributeName)` -- https://developer.mozilla.org/en-US/docs/Web/API/Element/getAttribute
- `element.setAttribute(attributeName,attributeValue)` -- https://developer.mozilla.org/en-US/docs/Web/API/Element/setAttribute
- `element.appendChild(anotherElement)` -- https://developer.mozilla.org/en-US/docs/Web/API/Node/appendChild
- `element.insertBefore(referenceElement,anotherElement)` -- https://developer.mozilla.org/en-US/docs/Web/API/Node/insertBefore
- `element.removeChild(anotherElement)` -- https://developer.mozilla.org/en-US/docs/Web/API/Node/removeChild
- `element.replaceChild(oldElement,newElement)` -- https://developer.mozilla.org/en-US/docs/Web/API/Node/replaceChild
- `element.hasChildNodes()` -- https://developer.mozilla.org/en-US/docs/Web/API/Node/hasChildNodes

And some properties:

- `document.body` -- https://developer.mozilla.org/en-US/docs/Web/API/Document/body
- `element.parentNode` -- https://developer.mozilla.org/en-US/docs/Web/API/ParentNode
- `element.children` -- https://developer.mozilla.org/en-US/docs/Web/API/ParentNode/children

## II. Starter Page

### more-dom-1.html
```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>More DOM 1</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Page</h1>
<h2>Info</h2>
<p>Blah <b>Blah</b> Blah</p>
<h2>Links</h2>
<ul>
	<li><a href="http://www.apple.com">Apple</a></li>
	<li><a href="http://www.google.com">Google</a></li>
</ul>

<script>

</script>
</body>
</html>
```

**Looks like this in the browser:**

![Web Page](_images/more-dom-1.jpg)

## III. Creating and appending elements
Our page is missing a &lt;footer>, so let's create one and insert it into the &lt;body>, and the very end of the page. 

### more-dom-2.html

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>More DOM 2</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Page</h1>
<h2>Info</h2>
<p>Blah <b>Blah</b> Blah</p>
<h2>Links</h2>
<ul>
	<li><a href="http://www.apple.com">Apple</a></li>
	<li><a href="http://www.google.com">Google</a></li>
</ul>

<script>
	// 1 - Create a <footer> element
	let footer = document.createElement("footer");
	
	// 2 - set the title attribute, which gives us a tooltip 
	footer.setAttribute("title","Don't copy this page without my permission!");
	
	// 3 - create the text of the <footer>
	let textNode = document.createTextNode("© 20XX by Ima Student");
	
	// 4 - insert the text into the <footer> element
	footer.appendChild(textNode);
	
	// 5 - insert the <footer> at the end of the <body>
	document.body.appendChild(footer);
</script>
</body>
</html>
```

**Load the page into a browser, you should now see the new &lt;footer> at the bottom of the page, and the tooltip effect!:**

![Web Page](_images/more-dom-2.jpg)

## III. Creating and appending elements, with a little less code

We can simplify this code though, by using `.innerHTML` instead of `document.createTextNode()`, and other changes. See below:

### more-dom-3.html

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>More DOM 3</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Page</h1>
<h2>Info</h2>
<p>Blah <b>Blah</b> Blah</p>
<h2>Links</h2>
<ul>
	<li><a href="http://www.apple.com">Apple</a></li>
	<li><a href="http://www.google.com">Google</a></li>
</ul>

<script>
	// 1 - Create a <footer>
	let footer = document.createElement("footer");
	
	// 2 - set the title attribute, which gives us a tooltip 
	footer.setAttribute("title","Don't copy this page without my permission!");
	
	// 3 - create the text of the <footer>
	let textNode = document.createTextNode("© 20XX by Ima Student");
	
	// 4 - insert the text into the <footer>
	footer.appendChild(textNode);
	
	// 5 - insert the <footer> at the end of the <body>
	document.body.appendChild(footer);
	
	// 6 - this code does the same thing as #1-#5 above, without having to use
	// document.createTextNode() or element.setAttribute()
	
	// add another <footer>, with less code!
	let footer2 = document.createElement("footer");
	footer2.title = "Don't copy this page without my permission!";
	footer2.innerHTML = "&copy; 20XX by Ima Student"
	document.body.appendChild(footer2);
	
</script>
</body>
</html>
```

**Load the page into a browser, you should now see the second &lt;footer>:**

![Web Page](_images/more-dom-3.jpg)


## IV. Inserting elements into the middle of a DOM tree
Rather than just append everything to the bottom of the &lt;body>, let's see how to add elements to both the end and the middle of an unordered list.

### more-dom-4.html

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>More DOM 4</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Page</h1>
<h2>Info</h2>
<p>Blah <b>Blah</b> Blah</p>
<h2>Links</h2>
<ul>
	<li><a href="http://www.apple.com">Apple</a></li>
	<li><a href="http://www.google.com">Google</a></li>
</ul>

<script>
	// 1 - Create a <footer>
	let footer = document.createElement("footer");
	
	// 2 - set the title attribute, which gives us a tooltip 
	footer.setAttribute("title","Don't copy this page without my permission!");
	
	// 3 - create the text of the <footer>
	let textNode = document.createTextNode("© 20XX by Ima Student");
	
	// 4 - insert the text into the <footer>
	footer.appendChild(textNode);
	
	// 5 - insert the <footer> at the end of the <body>
	document.body.appendChild(footer);
	
	// 6 - this code does the same thing as #1-#5 above, without having
	// to use document.createTextNode() or element.setAttribute()
	
	// add another <footer>!
	let footer2 = document.createElement("footer");
	footer2.title = "Don't copy this page without my permission!";
	footer2.innerHTML = "&copy; 20XX by Ima Student"
	document.body.appendChild(footer2);
	
	// 7 - create a new <li> and insert it into the end of the <ul>
	let listItem = document.createElement("li");
	listItem.innerHTML = "GeoCities";
	
	let unorderedList = document.querySelector("ul");
	unorderedList.appendChild(listItem);
	
	// 8 - create a new <li> and a new <a>, and insert them before the Google link
	// 8A - create an <li> with a link in it
	let fbListItem = document.createElement("li");
	let link = document.createElement("a");
	link.innerHTML = "Facebook";
	link.href = "http://www.facebook.com";
	fbListItem.appendChild(link)
	
	// 8B - get a reference to the google list item
	let googleListItem = document.querySelector("ul li a[href*='google.com']").parentNode;
	
	// 8C - insert the Facebook link before the Google list item
	unorderedList.insertBefore(fbListItem,googleListItem);
	
</script>
</body>
</html>

```

### The new code here is in #7 and #8. 

- #7 creates a new &lt;li> with the text "GeoCities" and appends it to the end of the list.
- #8A creates a new  &lt;li> and a new "Facebook" &lt;a>, and appends the &lt;a> to the &lt;li>
- #8B gets a reference to the "Google" &lt;li> (note the cool CSS selector and the `.parentNode` property), and then inserts the "Facebook" &lt;li> before it.


**Load the page into a browser, you should now see the 2 new list items, one of which is a functioning link to Facebook:**

![Web Page](_images/more-dom-4.jpg)


## V. Modifying Existing DOM Elements

Modifying the properties and styles of existing DOM elements is easy. Add the following to the end of **more-dom-4.html**:

```
// 9 - Modify the google link's href
let googleLink = document.querySelector("ul li a[href*='google.com']");
googleLink.href = "http://www.bing.com";
```

- Reload the page and click the Google link - it should now send you to www.bing.com - don't tell Google about this as they might come after you!

- You can also open up the web inspector to verify that the value of the Google link's href is now `http://www.bing.com`



## VI. Removing Existing DOM Elements

Removing DOM elements is trivial. Add the following to the end of **more-dom-4.html**:

```
// 10 - Delete the paragraph
document.body.removeChild(document.querySelector("p"));
```

- Reload the page - the paragraph is now gone. You can also see this in the Web Inspector. 


## VII. Review Questions

Be sure to read the HTML DOM page linked near the top of this document.

1. Exactly how many *parent* elements can an element on a web page have?
1. What are the *child* elements of the &lt;ul> tag in **more-dom-4.html**?
1. What is the *first-child* of the &lt;ul> tag in **more-dom-4.html**?
1. What is the *last-child* of the &lt;ul> tag in **more-dom-4.html**?
1. What is the *next-sibling* of the "Google" &lt;li> tag in **more-dom-4.html**?
1. What is the *previous-sibling* of the "Google" &lt;li> tag in **more-dom-4.html**?
1. What is the *first-child* of the "Google" &lt;li> tag in **more-dom-4.html**?
1. What is the *parent* of the "Google" &lt;li> tag in **more-dom-4.html**?

## VIII. Review Exercise

Here is your starter code:

### web-apps-4.html

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title>Web Apps-4</title>
	<style>
		body{border:1px solid gray;}
	</style>
</head>
<body>
<h1>My Links</h1>
<h2>My Favorite Colors</h1>

<ol id="colorsList">
	
</ol>

<h2>My Favorite Foods</h1>

<ol id="foodsList">
	
</ol>

<h2>My Favorite Links</h1>

<ol id="linksList">
	
</ol>

<script>
let colors = ["red","green","blue","purple","pink"];
let foods = []; // add some foods

// Optional (worth an extra 5 points) - can you figure out how to pull the key
// and value from the links obejct literal?
let links = {
		"RIT": "http:www.rit.edu",
		"RWAG" : "https://www.facebook.com/RWAGclub",
		"New Media Club" : "http://newmediaclub.cias.rit.edu"
	}

</script>
</body>
</html>
```

### Instructions
1. Create the **web-apps-4.html** file
1. Add you favorite colors and foods to the arrays. If you would rather change the theme of the page to movies, music, books or similar, feel free.
1. Write code that loops through these arrays, generates list items, and appends them to the appropriate list element.
1. Be sure that your code uses `document.createElement()` to create each element.
1. Optional: add your favorite web sites to the links object literal, and then loop through the object, pulling out both the key and the value, generate functioning links, and add them to the last &lt;ul> on the page. This is worth an extra 5 points on the HW assignment.

### Final Result

**It should look like this, except with your favorites (whatever they are):**

![Web Page](_images/more-dom-5.jpg)
