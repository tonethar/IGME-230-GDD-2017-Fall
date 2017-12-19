# 1 - Introduction to Web Applications
## Overview
First we will discuss what a *web app* is, and take look at the different components of a web browser that a developer is able to program.

## Contents
<!--- Local Navigation --->
I. [What is a "Web App"?](#section1)

II. [What parts of the web browser can I program?](#section2)

III. [Web APIs used in the IGM Web Courses](#section3)

IV. [How do I know what browser APIs I can use in my web applications?](#section4)

V. [Discussion/Review](#section5)

<hr><hr>

## I. <a id="section1"></a>What is a "Web App"?

The wikipedia definition - https://en.wikipedia.org/wiki/Web_application - is pretty good - *A web app is a client–server computer program in which the client (including the user interface and client-side logic) runs in a web browser. Common web applications include webmail, online retail sales, online auctions, wikis, instant messaging services and many other functions.*

In this course we are going to create some simple web apps that run in modern web browsers. 
The examples we will build include a calculator, an image gallery, an app that can search/download/play song previews from a music service, and simple games.
Most of these apps will run entirely in the *client* (i.e. the web browser). Others (the music player) will utilize data downloaded from the Internet. 

## II. <a id="section2"></a>What parts of the web browser can I program?

If we are going to build applications that run in web browsers, we need to understand the major components of the browser that can be scripted by us.

1. The **Web Layout Engine** - each browser has a layout engine that renders (draws) marked up content by utilizing formatting information. We have already been doing this with **HTML** (a markup language that adds structure and meaning to the content on our web pages) and **CSS** (a presentational language that adds colors, fonts, spacing, etc).
Each major web browser has its own layout engine: Chrome and Opera have *Blink*, Safari has *WebKit*, FireFox has *Gecko*, and Edge has *EdgeHTML*. There are subtle differences between these engines, and they adopt new and experimental features at different times, but the distinctions between them have been lessening over time. (You can read more about layout engines here: https://en.wikipedia.org/wiki/Web_browser_engine)

1. The **JavaScript Engine** - this is a program that executes JavaScript code in the web browser. Each browser vendor has their own distinct engine: Chrome has V8, Safari has Nitro (JavaScriptCore), and FireFox has SpiderMonkey. These engines have performance differences and differing support for newer JavaScript language features. You can read more about JavaScript engines here: (https://en.wikipedia.org/wiki/JavaScript_engine)

1. **Web Browser APIs** - API stands for "Application Programming Interface" and reflects what a web browser can *do*. JavaScript would not be very useful thing in a web browser if not for the various APIs that are available in today's web browsers. These APIs include the ability to select and modify HTML elements on the page (which effects the *Web Layout Engine above*), to play audio and video, to do procedural drawing, to store application data locally (in the web browser), to send and receive files from remote servers, and more. A mostly complete list of browser APIs can be found here: https://developer.mozilla.org/en-US/docs/Web/API

## III. <a id="section3"></a>Web APIs used in the IGM Web Courses
Here are some of the Web APIs that you will be using in this course and/or the following web course (IGME-330):
- **Canvas** - procedural drawing and animation -  https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API
- **Document Object Model (DOM)** - used to access and modify the contents and style  of a web page - https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model
- **Fetch** and **XMLHttpRequest** - used to fetch resources over a network - https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API & https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest
- **Web Audio** - analyze and add effects to audio such as reverb and panning, or create periodic waveforms from scratch using `OscillatorNode` - https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API
- **Web Storage** - store key/value pairs of data in the user's browser - https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API


## IV. <a id="section4"></a>How do I know what browser APIs I can use in my web applications?
As developers we want to create applications that take advantage of the latest browser features, but also don't leave users of more recent browsers behind. This can be a challenge because the various web browser vendors adopt new features at different times. 
Sometimes new features are adopted long after *web standards* bodies have approved them, other times browser vendors will implement experimental features prior to a standard being agreed upon.

### a. What are the major main web standards bodies?
Because no one company or organization is in charge of deciding what features a browser vendor want to add to their web browser, several web standards bodies have formed. *Web standards are rules and guidelines published by standards bodies that are designed to promote consistency in the behavior of web browsers.*  Once a standard has reached "Recommendation" status its features are usually quickly adopted by the major web browsers.

For example, Firefox might adopt a new feature (browser capability), then Chrome and Safari copy it but design their APIs in a slightly different way. If a proposed feature seems to be gaining popularity, the standards bodies will begin to formalize the API of the new feature, and gather feedback from both the browser vendors and the broader developer community.

- World Wide Web Consortium (W3C) - https://www.w3.org/standards/webdesign/
- Web Hypertext Application Technology Working Group (WHATWG) - https://spec.whatwg.org

**Other readings about standards:**

- the Web Standards Project here: https://www.webstandards.org
- "Implementations and specifications have to do a delicate dance together." - http://lists.w3.org/Archives/Public/public-html/2010Jan/0107.html
- the "A LONG DIGRESSION INTO HOW STANDARDS ARE MADE" section here: http://diveintohtml5.info/past.html


### b. Where can I learn about new features the browser vendors are working on?
Checking out the browser vendor web sites is a good way to see what kinds of capabilities are being considered.
- https://www.chromium.org/blink
- https://developer.mozilla.org/en-US/docs/Mozilla/Gecko
- https://webkit.org
- https://developer.microsoft.com/en-us/microsoft-edge/

### c. Where is the official web documentation located?
Because there is not one central authority on web standards, and the capabilities of the browsers are constant changing, documentation is spread throughout the Internet. Here is the best source of web standard documentation (other than the actual specifications): 
- https://developer.mozilla.org/en-US/docs/Web/Guide

But when in doubt, you should be brave and read the actual specifications :-)
- https://html.spec.whatwg.org/multipage/
- https://www.w3.org/html/
- https://www.ecma-international.org/ecma-262/

### d. What's an easy way to keep all of this straight?
The best web site for tracking the adoption of new browser capabilities: 
- http://caniuse.com 

## V. <a id="section5"></a>Discussion/Review
1. What is a *Web App*?
1. What are the 3 major components of a web browser that can be scripted/controlled by a web developer?
1. What languages are commonly used to "program" the **Web Layout Engine**?
1. How are new web browser features proposed?
1. Who is in charge of web standards - the standards bodies or the browser vendors?
1. List 3 places a web developer can find "web app" documentation.

<hr>

**[Table of Contents <- About this Web App Tutorial Series](web-apps-0.md)**

**[Next Chapter -> Intro to JavaScript (chapter 2)](web-apps-2.md)**
