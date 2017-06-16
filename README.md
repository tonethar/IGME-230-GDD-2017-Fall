# IGME-230 Web Site Design & Implementation, Fall 2017: Syllabus

## Course Catalog Description 
*This course provides an introduction to web development tools and technologies, such as X/HTML, CSS, Javascript and DHTML, AJAX, web platforms and environments, and server-side programming methods.*

## Prerequisites
IGME-110 Introduction to Interactive Media & IGME-106 Game Development and Algorithmic Problem Solving II (GDAPS II). We expect students in this class to have a basic working knowledge of HTML, CSS, and publishing to RIT's web hosting environment (banjo.rit.edu). As this course involves a significant amount of coding, you should also feel confident in your coding skills. 

## Course Materials and Communication
There is no required textbook for the course, but there will be an assortment of handouts and online readings that you will receive over the course of the semester. They will be uploaded to (or linked from) this Github site. 

We will be assigning a number of tutorials from the [Lynda.com](http://lynda.com) website, which you can access for free using your RIT login. 

Most course materials and example code will be distributed via Github, and you will also be learning how to use Git and Github to manage your own exercise and project files.

MyCourses will also be used for announcements, certain assignment submissions, and grading.

## Attendance
Attendance is mandatory and you are expected to be on time. Lectures will start promptly at the beginning of class, and will be followed by an in-class assignment or exercise that you are expected to work on until the end of the meeting (i.e. no leaving early).

## Grading
| Class Average | Grade |
| ------------- | ----- |
| 90+%	| A |
| 80+%	| B |
| 70+%	| C |
| 65+%	| D |
| <65%	| F |

### Policy on Incomplete Grades
Incomplete grades will be given only in the most exceptional circumstances, and only for issues that arise AFTER the 'W' deadline has passed at the end of week 12, and then only by prior arrangement with the professor. Being overcommitted, overwhelmed, and/or not having enough time to complete your coursework is not sufficient justification for an "I". Instead, meet with the professor ASAP as early as possible in the semester if you're having difficulty. 

### Academic Dishonesty
The course policy on academic dishonesty is simple: If you get caught cheating or plagiarizing, you get an "F" as a grade for the course, a letter detailing the incident goes into your records folder, and you are immediately removed from the class. (If this is a second occurrence during your career at RIT, the penalties are harsher.) Please review RIT's policy on academic dishonesty: 
[http://www.rit.edu/~w-policy/sectionD/D8.html](http://www.rit.edu/~w-policy/sectionD/D8.html)

### Important RIT Deadlines
- Last day of add/drop is Tuesday Sept. 5th, 2017.
- Last day to withdraw with a grade of "W" is Friday Nov. 10th, 2017.
- Grades of "I" (Incomplete) 
- You have one semester after the class has ended to challenge your grade. 


(End of student Syllabus)
<hr>
(Beginning of course notes)

## Topics
* Module 0
  * Why this course matters
  * Review (**Sean will post 110 files to mycourses.rit.edu**) 
    * (They should already know - post 110 web exercises to mycourses)
    * Basic HTML/CSS
    * Posting to Banjo
    * CRAP
    * ssh & basic Unix commands
    * Image Basics (compressed v. uncompressed, formats)
    * Photoshop - cropping & scaling images, exporting in proper formats
* Module 1 - Basic Web Publishing (**Sean will handle**) 
  * Web Servers:
    * HTTP Protocol: request phase, response phase, status codes, headers, content-type
    * .htaccess file directives: Modpagespeed, Redirect, ErrorDocument, Authorization, Option +Indexes
  * HTML5 Semantic Tags
  * CSS 3 Selectors
  * CSS for layout
  * Responsive Design - Darth ICE or Similar
  * GitHub
  * HW: Custom 404 Page, authentication
  * Project: Multi-page web site for their game
* Module 2 - Client/Server Interactive Applications
  * ICE: Calculators
  * ICE: ToDo List using web storage
  * PHP Basics - dynamic web pages, passing arguments to PHP, includes
    * Demos: info.php, who-am-i.php, redirect.php (PHP can send headers), hello.php, hello-with-args.php, logger.php (embedding PHP in a regular HTML page) 
  * PHP to use with JavaScript:
    * add-score.php, get-high-scores.php (shared high scores)
    * web-service.php (returns JSON data based on value passed in via query string)
  * HTML Widgets (dropdowns, inputs)
  * ICE: JS App that loads and displays our web-service.php data
  * ICE: Web Service ICE (Ajax via jQuery, utilizes iTunes Music web service, JSON format)
* Module 3 - Client-side DOM Games (Typing Game, Concentration, Snake, Magnetic Poetry, etc)
  * More CSS for layout
  * CSS Transforms
  * CSS Animations
  * Basic JavaScript: variables & scope, loops, conditionals, functions, arrays
  * DOM Methods: querySelector(), querySelectorAll(), createElement(), setAttribute(), .innerHTML
  * requestAnimationFrame() for timing
  * events: addEventListener(), load, click, change
  * HTML 5 Web Storage for local high scores
  * ES6: let, block scoping, classes, arrow functions, string templating, for/of
  * Project DOM Game or Interactive Application
* Module 4 - Building a Portfolio (thoughout semester, several deliverables)
  * (By this point, students should be very comfortable with HTML/CSS/JS, so the Lynda.com Bootstrap tutorials will be easy to follow)
  * Reinforce Responsive Design
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
* Project 1 - Game Proposal Site - #1 Deliverable is content posted to GitHub.
* Project 2 - Educational DOM Game or Web Application
* Project 3 - Interactive Game Or Experience (Sprite Based)
* Capstone Project - Web Portfolio. #1 Deliverable is content posted to GitHub.

## Links
* [Learning Pixi](https://github.com/kittykatattack/learningPixi)
* [Exploring ES6](http://exploringjs.com/es6/index.html)

## Notes
* Homeworks need more "challenges" to earn 10/10. The paint-by-numbers portions of ICEs should be worth just a few points.
* We should use Lynda.com videos where possible, but if it an essential topic, make sure that there is a solid assignment that goes along with the video (ex. "watch sections 2 & 3 of the XX video, and then utilize a media query on your home page to modify the heading size of your home page for devices less that 550 pixels wide.")
* Introduce JS earlier so that they can do more with Bootstrap
