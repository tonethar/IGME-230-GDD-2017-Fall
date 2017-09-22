# Project 1 - Game Proposal Site #
For project 3, you will be making a web game or "experience." To get you started thinking about this early, for Project 1 you'll be building a site to promote and document a web game project. For the purposes of project 1, don't worry too much about the scope of the game, or the fact that your specs will probably change. Just think about what you might want to make. (But when looking ahead to Project 3, when you actually have to build something, I suggest you keep an eye on the web for what sorts of apps and games other people are making that are small enough in scope for you to build in the span of a few weeks.)

## Requirements ##
Location: The page will be located in the project1 directory in your 230 directory on Banjo. This means that the location of page on the web will be http://people.rit.edu/abc1234/230/project1/ (where 'abc1234' is your RIT id), as shown below:

![Structure](images/Project1Structure.png)

Your main page for the tutorial will be the index page for this directory. You must have css and media directories to store the associated files. **Remember**: Our server is case sensitive, so your files must use the case indicated in this assignment. 

## Content and Structure ##
Content is the foundation of the Web; all pages exist to present some content, not the other way round. For this reason, your content needs to be written **first**. Your primary content is a *game design treatment* containing most or all of the information found on this template: http://igm.rit.edu/~acjvks/courses/2017-fall/590-ios-game/html/project-1-proposal.html


By the beginning of the first class of week 4, your content must be written, chunked, and organized, and posted to your repo on GitHub as a markdown file named `230-project-1-content.md`. We will be checking this, and you need to **do your best work** as the content is weighted heavily on the rubric (see below)! Once this is done, begin building your HTML structure to fit the content (populating it with dummy content). Only when the structure is finalized should you be putting in the actual content!

Note: If you have never use markdown before, it's extremely easy to work with. We will be doing a quick demo in class, and you might find this markdown "cheatsheet" handy: https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet

## Required Content ## 
- The following pages (each in separate HTML files):
  - **index.html**: your "landing" page (the default file for your project1 directory):
    - This page must have a brief overview of your project, contain at least one image, and most importantly grab the user's attention.
  - **proposal.html**: what you plan to do, in more detail than the overview:
    - This page will be a game design document, specifically a *game treatment* that describes the development side of your game. This page is not a marketing document.
    - You should be hitting most or all of the things on this template: http://igm.rit.edu/~acjvks/courses/2017-fall/590-ios-game/html/project-1-proposal.html - you can also read more about game treatments here: http://thelegendofjohnny.com/tutorials/game-treatment
    - This page will be marked up heavily with structural and semantic tags, some of which are listed below.
    - This page will contain at least two images.
  
  - **documentation.html**: A documentation page, which will document your overall process, resources used, and notes about this current assignment. Cite the sources of all information, tutorials, images and other media used. Also indicate how you met the project requirements, and any additional specifics you want me to see.
  - **project.html**: The game or app itself (the content will just be a placeholder for now, but the page needs to have the same look and navigation as the other pages)
  
## HTML/CSS Markup ##
-	Structural tags like `<header>`, `<section>`, `<article>`, `<nav>`, and `<footer>` should be used appropriately.
- Try to use a consistent structure on all of your 4 pages by repeating many of your design elements - for example: the `<header>`, `<footer>` and `<nav>` elements should be in the same places on each page and have the same colors, fonts and spacing.
- Be sure to have descriptive `<title>` elements for each page.
-	CSS selectors and rules will be used for formatting and positioning: 
  - Most of the style rules will be located in an external style sheet.
  -	There will be at least 5 style declarations (rules) in your external style sheet. 
    -	At least one of these style declarations will utilize a *class selector*.
    -	At least one of these style declarations will utilize an *id selector*.
    - Utilize custom link styles on all your pages by utilizing the `a:link`, `a:hover`, `a:active` and `a:visited` selectors. (These 4 selectors do not count towards the 5 style rule requirement above)
  - Avoid using *inline* styles.

## Design ## 
- College-level work
- Professionally styled  so that so that the results are pleasing and in no way resemble any templates or in-class exercises. The page design will be well thought out with appropriate organization, spacing, colors and fonts, and all pages should be consistent in look, feel and navigation.
-	Design principles (e.g. CRAP) applied appropriately.
- Navigation should be consistent across all pages, with a single, unified nav scheme, with all global nav in the same place on every page
  - Good navigation should always answer the questions "Where am I?" and "Where can I go?" This means your nav should **always** be the same on every page; don't make a link go away just because the user is on the page it links to.
- Text should be of sufficient size and contrast to be easily readable
- Responsive Design: 
  - At a minimum, you must support screen sizes equal to or less than max-width: 480px
  - Your design should be re-formatted to support these smaller screens. Changing font-size, margins, moving side bars, hiding elements, and ??? are all options.

## Other Requirements ##
- Do not use an HTML/CSS template that you found on the web or elsewhere! Build the HTML and CSS yourself "from scratch". Ignoring this requirement will result in a zero on the assignment and possible other academic integrity consequences.
- HTML tables used only for tabular data, not page layout.
- No plugin content (Flash, et al.)
- Site is fully accessible even without graphics enabled (e.g., use the `alt` attribute for all images)
- Images are not resized via code; all images must be at their native resolutions. If you need an image to be smaller, resize it in your graphic editor of choice.
- Images must be saved in the appropriate web-friendly format i.e. Photographs are usually saved as jpegs, presentational web graphics are saved as PNGs or GIFs.

# Critique Session #
The second class of week 5, we will have a critique session in class. In small groups, you will both give and receive feedback on your projects, so be prepared for this discussion.
While the critiques aren’t going to directly determine your project grade, the feedback you receive will be taken into consideration, so make sure your project is built to impress!

# Final Submission #
After receiving feedback from your classmates, make fixes and improvements to your site, and post it to Banjo before midnight on Friday of week 5.

**Submission:** Post to Banjo - be sure to test that it works in a Web browser. I must be able to get to it from your page when I click your name in my class list, so make sure to link to it from your main page. If your main page doesn't load when I click my link, or I can't immediately find a way to get to your project from that main page, you will get a 0 for the project. Please check when you upload it!

# Grading #
Reminder - 'A' -level work means doing college-level work that goes beyond what we did in class. Meeting only the base requirements will most likely only earn you a B. In order to get an A, you need to impress! Also make sure that this is 100% your work - no templates or frameworks are allowed

Your project will be graded on the following criteria:

| Criteria | Weight | Your Score |
| -------- | ------ | ---------- |
| The game treatment content is substantial, informative and written at the college level (including correct spelling, grammar, and punctuation); includes required content and all required pages | 20 | |
| All pages and support files are appropriately named and mounted in the correct directories with correct file permissions | 5 | |
HTML and CSS are appropriately used and well formed, clean, accurate, etc.; images are not resized in HTML, tables aren't used for layout, and there aren't unnecessarily large blocks of commented code | 10 | |
| Appropriate use of HTML structures to describe pages (```<title>, <nav>, <header>, <footer>```, etc.) and organize content (headers, lists, etc.)  | 10 | |
| HTML validates correctly (HTML5) | 5 | |
| At least 5 CSS style declarations are used to control formatting, and stored in an external stylesheet| 5 | |
| CSS Selectors: the external style sheet must use at least one *class* and one *id* selector | 5 | |
| CSS validates correctly (CSS3) | 5 | |
| Uses images appropriately (proper format, dimensions, and file size) | 5 | |
| Overall aesthetic (use of font, color, image, CRAP principles, etc.) is appropriate for this type of site; all necessary items are styled, no default link colors | 15 | |
| Site is fully accessible even without graphics enabled | 5 | |
| Responsive design supports viewports as low as 480px wide | 10 | |
| **Possible Total Points** | **100** | |
| Deduction if initial checkpoint is not submitted to GitHub on time | -10 | |
| Deduction if project is not ready for critique | -10 | |


