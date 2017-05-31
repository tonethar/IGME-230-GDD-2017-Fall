# IGME-230 Web Site Design & Implementation (GDD)
#### (DRAFT as of 5/31)

## Current Course Description
*This course provides an introduction to web development tools and technologies, such as X/HTML, CSS, Javascript and DHTML, AJAX, web platforms and environments, and server-side programming methods.*

## Current CPF Outcomes
* *Students will use standards-compliant markup languages and style sheets to implement web pages.*
* *Students will use client-side techniques such as JavaScript to implement interactivity and navigation.*
* *Students will use server-based techniques including .htaccess directives and server-side scripting to improve site performance and security.*
* *Students will demonstrate proficiency with fundamental data access from server-side scripts.*

## Other outcomes beyond CPF
* Students will work in groups and collaborate utilizing a version control system.
* Students will publish a web portfolio of their best GDD work to date.
* Students will create an interactive web application that displays & filters data retrieved from a server.
* Students will be able to create simple web games using both DOM technologies and a rendering engine (Pixi.js)

## Topics
* Module 0
  * Why this course matters
  * Review
    * (They should already know - post 110 web exercises to mycourses)
    * Basic HTML/CSS
    * Posting to Banjo
    * HTML Tables
    * CRAP
    * ssh & basic Unix commands
* Module 1 - Basic Web Publishing
  * Web Servers:
    * HTTP Protocol: request phase, response phase, status codes, headers, content-type
    * .htaccess file directives: Modpagespeed, Redirect, ErrorDocument, Authorization, Option +Indexes
  * HTML5 Semantic Tags
  * CSS 3 Selectors
  * CSS for layout
  * GitHub
  * HW: Custom 404 Page, Secret Page
  * Project: Multi-page web site for their game
* Module 2 - Client-side DOM Games (Typing Game, Concentration, Snake, Magnetic Poetry, etc)
  * More CSS for layout
  * CSS Transforms
  * CSS Animations
  * Basic JavaScript: variables & scope, loops, conditionals, functions, arrays
  * DOM Methods: querySelector(), querySelectorAll(), createElement(), setAttribute(), .innerHTML
  * requestAnimationFrame() for timing
  * events: addEventListener(), load, click, change
  * HTML 5 Web Storage for local high scores
* Module 3 - Client/Server Interactive Applications
  * PHP Basics - dynamic web pages, passing arguments to PHP
    * Demos: info.php, who-am-i.php, redirect.php (PHP can send headers), hello.php, hello-with-args.php, logger.php (embedding PHP in a regular HTML page) 
  * PHP to use with JavaScript:
    * add-score.php, get-high-scores.php (shared high scores)
    * web-service.php (returns JSON data based on value passed in via query string)
  * HTML Widgets (dropdowns, inputs)
  * ICE: Calculators
  * ICE: ToDo List using web storage
  * ICE: JS App that loads and displays our web-service.php data
  * ICE: Web Service ICE (Ajax via jQuery, utilizes iTunes Music web service, JSON format)
  * Project DOM Game or Interactive Application
* Module 4 - Building a Portfolio
  * (By this point, students should be very comfortable with HTML/CSS/JS, so the Lynda.com Bootstrap tutorials will be easy to follow)
  * Darth ICE or Similar
  * Responsive Design
  * Bootstrap
  * Discuss publishing to GitHub Pages, LinkedIn, Behance, etc ...
  * Portfolio Project - Single Page Responsive App published to Banjo
* Module 5 - Interactive Graphics
  * More JS: Object Literals, 
  * PixiJS
  * Game Project

## Specific knowledge gained by end of course
* HTML
  * HTML 5 Sematic Tags
  * input tags
* CSS
  * Selectors: type, class, id, some CSS 3 selectors
  * CSS Rollovers
  * Media Queries
  * CSS 3 Animations
* Basic JavaScript
  * variables & scope
  * data types
  * loops
  * conditionals
  * functions
  * arrays
  * object literals
* DOM
  * Objects: window, document, body
  * Methods: querySelector(), querySelectorAll(), addEventListener()
  * Events: onload, onclick, onchange
* Graphics Rendering
  * PixiJS
* Collaboration
  * GitHub
* Web Applications
  * Ajax
  * jQuery
  * JSON
* Web Design
  * Navigation
  * Single-Page Design
  * Responsive Design
* Web Publishing
  * FTP to banjo
  * GitHub pages
  * LinkedIn?
  * portfolios.rit.edu?
  * behance.net?

## Projects
* Project 0 - 230 Home Page? (Gradable by TA)
* Project 1 - Web Portfolio
* Project 2 - ???
* Project 3 - Interactive Game Or Experience

## Links
[Learning Pixi](https://github.com/kittykatattack/learningPixi)

## Notes
* Homeworks need more "challenges" to earn 10/10. The paint-by-numbers portions of ICEs should be worth just a few points.
* We should use Lynda.com videos where possible, but if it an essential topic, make sure that there is a solid assignment that goes along with the video (ex. "watch sections 2 & 3 of the XX video, and then utilize a media query on your home page to modify the heading size of your home page for devices less that 550 pixels wide.")
* Introduce JS earlier so that they can do more with Bootstrap
