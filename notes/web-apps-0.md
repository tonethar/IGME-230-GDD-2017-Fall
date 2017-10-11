# About this Web App Tutorial Series
## I. Overview
This series of tutorials/lecture notes will get you started in creating web applications, which are *client-server* applications in which the client code runs in a web browser. 

## II. Prerequisite knowledge
- The HTML/CSS which we covered in this class
- CSS selectors (in particular the CSS3 selectors) will come in handy
- Fundamental programming concepts that you gleaned from the (at least) 2 programming classes you have taken prior to this course.

## III. How to get the most out of these tutorials
- Try out the code samples! Tweak and modify them! Most of the code samples are 100% complete. You just need to copy the code and paste it into a text file, and save it to your desktop. You can then make changes to the code and preview them in a web browser (we will be using Chrome)
- Be sure to answer all of the questions at the end of each section, and to do the review exercises.

## IV. The Tutorials
1. [Introduction to Web Applications](https://github.com/tonethar/IGME-230-GDD-2017-Fall/blob/master/notes/web-apps-1.md):
    1. what is a web app?
    1. what components of the web browser can I program?
    1. what are web standards?
1. [Introduction to JavaScript](./web-apps-2.md)
    1. a brief history of JavaScript
    1. variables, constants, and types
    1. running code in the JavaScript console
    1. viewing error messages in the JavaScript console
    1. common built-in JavaScript objects
1. [Introduction to the Web Browser DOM](./web-apps-3.md)
    1. did the HTML elements on the page load?
    1. selecting elements on a web page
    1. modifying elements on a web page
    1. add elements to a page, primarily with `.innerHTML`
    1. viewing the "live" DOM tree with the web inspector
    1. using the JavaScript debugger to "break on exceptions"
    1. adding code breakpoints in the JavaScript debugger
    1. viewing the value of variables in the JavaScript debugger
1. [More Web Browser DOM Methods](./web-apps-4.md)
    1. the DOM inverted tree
    1. relationships: parent, child & sibling
    1. creating and modifying DOM elements
    1. inserting and deleting DOM elements from the DOM tree
1. [JavaScript Functions](./web-apps-5.md)
    1. Writing basic functions
    1. Function declarations & expressions
    1. Functions as *first-class* objects
    1. ES6 Block & Script Scope
    1. ES6 Arrow Functions
    1. More practice with the debugger
1. [JavaScript Events & the `this` keyword](./web-apps-6.md)
    1. Event Handlers
    1. Utilizing function declarations, expressions, and arrow functions
    1. `addEventListener()`, `removeEventListener()`
    1. Adding properties to elements with `element.dataset`
    1. Values of `this` in regular functions and arrow functions
1. [JavaScript Object Literals](./web-apps-7.md)
    1. Creating Object literals with properties and methods
    1. Iterating over object keys and values
    1. Creating "Object Factories"
    1. ES6 Object Literal changes
1. [JavaScript Arrays and array-like objects](./web-apps-8.md)
    1. methods of `Array`
    1. Looping through `Array` - `for`, `for...of`, `.forEach()`, `.filter()`, `.map()`
    1. `NodeList`
    1. JavaScript typed arrays
1. The WebStorage API
1. Intro to Web Services
    1. XHR & Fetch API
    1. AJAX v. Ajax
    1. JSON
1. JavaScript ES6 Classes

## V. Assignments
Refer to the dropboxes for due dates.
- [Random Phrases 1](./HW-random-phrases-1.md)
- [Random Phrases 2](./HW-random-phrases-2.md)
- [Image Gallery](./HW-image-gallery.md)
- [Magnetic Poetry](./HW-magnetic-poetry.md)
- [Pixel Artist](./HW-pixel-artist.md)
- ["GIF Finder" Web Service App](./HW-gif-finder.md)
- [Project 2](../projects/project2.md)

## VI. Demos
- ToDoList App
- Solitaire DOM Game

## VI. What has been left out of this series
This course is an introduction to web publishing and scripting the browser. Later courses with go deeper and cover more topics, and there is very much more that that to learn about web applications on your own. Here are some major topics that we are NOT covering:

- **Advanced JavaScript Concepts** will continue to be covered in downstream courses.
- **Canvas API** is covered in IGME-330.
- **Cloud Computing** is the practice of using a network of **remote servers** hosted on the Internet to store, manage, and process data. 
While we are going to utilize Internet resources in the form of web services, in this course our application code will be 100% on the client machine (the web browser). 
In later courses (IGME-330 & IGME-430) you will get the opportunity to read/write data to "the cloud", and even have application logic running on remote servers.
- **Database/Data Modeling** - creating a key:value server utilizing Node.js is covered in IGME-430 (an elective), *Data Modeling* and the SQL language are covered in ISTE-230 (an elective)
- **Package Managers** - such NPM & Bower and other build tools such as Gulp & Grunt are covered in later courses.
- **Web MVC Frameworks** - such as React and Angular are covered in later courses.
- **Web Games** will be covered later in this course, and we will build several games or interactive experiences using the PixiJS rendering engine.
- **WebGL** is an implementation of OpenGL ES 2.0 that runs natively in web browsers, and is the fastest way to draw to the browser screen. WebGL shaders may be briefly looked at while we are covering PixiJS.

## VII. Links & Resources


**[Next Section -> Introduction to Web Applications (part 1)](web-apps-1.md)**

