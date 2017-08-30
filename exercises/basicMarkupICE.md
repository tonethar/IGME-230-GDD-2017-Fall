# Basic HTML & CSS Exercise 

## Overview & Goals

In today's exercise, we will be taking a text document, marking it up as an HTML document, adding basic CSS formatting, and uploading it to your RIT web space. 

We will also be adding a configuration file to your RIT web space to override some of the server's (problematic) default behavior.

## Setting Up Your Folders and Files

On your computer (or on a USB drive) create a folder called igme230, and inside of the igme230 folder, create folder called week1. The igme230 folder is where all of your exercises and projects for this class will be stored. The week1 folder is for today's exercise. 

I've put uploaded a file called [cremebrulee.txt](cremebrulee.txt) to Github. When you click the link to view that file on Github, you'll see that it's a plain text file into which I've copied and pasted the content from the [Wikipedia entry for "Crème brûlée"](https://en.wikipedia.org/wiki/Cr%C3%A8me_br%C3%BBl%C3%A9e). 

To download that text file to your computer for editing, right-click on the button in the top right corner of the file that says "Raw," choose "Save link as...", and save the file to the week1 folder you just created.

You're also going to need to download the two images: [2014_0531_Crème_brûlée_Doi_Mae_Salong.jpg](2014_0531_Crème_brûlée_Doi_Mae_Salong.jpg) and [225px-Crema_Catalana_El_Glop.jpg](225px-Crema_Catalana_El_Glop.jpg). For each of those files, you will see a Download button in the top right corner. Right-click that button, choose "Save link as...", and download it to your local week1 folder. Then epeat that process with the second image, . 

## Setting Up VS Code

While you can use Visual Studio Code to open and edit a single file, it works best if you point it to your working folder. Launch the program, and use "Open Folder" to open the week1 folder. You should see the three files that you downloaded in the last step. 

There are two VS Code extensions that will be particularly useful in today's exercise:  Preview on Web Server, which I mentioned on Tuesday, and htmltagwrap, which allows you to select a block of text and easily wrap it with an HTML tag. To install the extensions now, choose View->Extensions, or click on the square icon at the bottom of the far left sidebar. In the search bar at the top, type in the name of the extension you want to add. When it appears, click the green "Install" button to add it. (If you're using Brackets, it already has a live preview built in, and you can install an extension called HTML Wrapper.) 

## Marking Up a Text File

Open the cremebrulee.txt file in your editor. It currently has no HTML markup at all--you're going to turn it into a proper HTML document, and add some simple CSS rules to make it look a bit more like the original Wikipedia entry. 

Use File->Save As... to save a new copy of the file called cremebrulee.html. Make sure you save it to the week1 folder and give it an .html extension--it's the extension that tells your editor to enable its HTML support. 

There are a lot of accented and foreign characters in this document. In HTML 4, the default character encoding for files was ISO-8859-1, which doesn't properly display special characters (like smart quotes and diacritical marks). Those characters had to be escaped out (e.g. &eacute; had to be represented as `&eacute;`, &copy; had to be represented as `&copy;`, and & had to be represented as `&amp;`)--if you didn't do that, they didn't display properly in the browser. HTML 5 uses UTF-8 encoding, which allows those special characters to appear properly in your document.

Because this Wikipedia article has many non-standard characters (like "smart" quotes and diacritical marks), the UTF-8 encoding is very helpful. If you're using VS Code, try clicking in the bottom right corner of the window where it says "UTF-8", choose "Reopen with encoding," and select ISO-8859-1. Note what happens to all the non-standard characters in the document! If your HTML document doesn't use a character set of UTF-8--which is the default for HTML 5, but not for previous versions of HTML--that's what will display on the page. (Switch back to UTF-8 before you proceed.) 

We're going to use Emmet, a shorthand tool for adding HTML and CSS content to documents, to simplify the adding of some basic HTML structure. (I talked about this at the beginning of class.)

Make sure there's a blank line at the top of your document, and type `html:5` (in VS Code, you should see a tooltip telling you this is an Emmet abbreviation). Then press TAB. The abbreviation should be replaced with the basic structure for an HTML 5 document. Cut and paste the document text so that it's inside the `<body>` tag. 

Now we need to mark the text up as HTML. (Use the actual wikipedia page as a refrerence.)

- Add an h1 heading for the page title, and h2 headings for all of the subsections.
- Add paragraph tags to the individual paragraphs of text. 
- Make the Contents and References sections into numbered ("ordered") lists, and the See Also, Bibliography, and External Links sections into bulleted ("unordered") lists. (Hint: Emmet can be very helpful with this, too!)
- Add the two images where indicated in the file, with appropriate alt text. Don't worry about positioning them for now; we'll deal with that when we add the CSS. 
- Use the `<sup>` tag to make each of the footnote references a superscript.
- Where appropriate, add tags to make text bold (`<strong>...</strong>`) and/or italicized (`<em>...</em>`).

Don't worry about adding links yet; we'll be doing that next week. 

Pay attention to the status bar at the bottom of the VS code window. If you see a number next to the triangle with an exclamation point, it means that VS Code has detected a problem with your code. If that happens, you can click on that number to see what the problem is. 

When you're done, preview your document (Ctrl-Shift-P or Ctrl-Shift-L in VS Code if you installed the Preview on Web Server extension). It should look something like this: ![Creme Brulee Page Without CSS](cremebrulee1.png)

## Publishing Your Files

*Note for New Media Design students: If you haven't ever uploaded files to banjo.rit.edu, which is the file server for the people.rit.edu web server, you should review the [prerequisite knowledge](../../README.md#prereq)) section in the syllabus (and emailed before the semester began). If you think you'll need a bit more time to get this exercise done, please contact me directly via private message on Slack or email to my Elizabeth.Lawley at rit dot edu address, and I'll grant you an extension until Sunday.*
 
Once you're satisfied with the html file, you're going to upload your igme230 folder (which includes your week1 folder and its contents) to your RIT web space. 

Using the SFTP program of your choice (the recommended option in the IGM labs is Filezilla), connect to the banjo.rit.edu server, and copy your entire igme230 folder into the www directory. (I'll demo this in class.)

Test it by going to `http://people.rit.edu/yourid/igme230/week1` -- you should see the .txt and .html files, and the two images. Click on the html file and make sure it displays properly. If you run into problems here, **ask for help ASAP**, in class, or via Slack. 

## Adding Basic CSS Formatting
Now we're going to use CSS to start to make the page look a bit more like the original Wikipedia entry.

Create a new file in the week1 folder called cremebrulee.css. Use Emmet to add a link to the stylesheet, by typing `link:css` and pressing tab. 

For today, since you've already done quite a bit of work, I'm going to give you the CSS to start with. Paste the following style rules into your cremebrulee.css file:

```
body {
    font-family: 'Helvetica Neue', Helvetica, Arial,sans-serif;
    line-height: 1.4;
    padding-left: 20px;
}

a { text-decoration: none; }

h1, h2 {
    font-family: 'Linux Libertine', Georgia, Times, 'Times New Roman', serif;
    line-height: 1.3;
    margin-bottom: 0.25em;
    padding: 0;
    border-bottom: 1px solid #a2a9b1;
    font-weight: normal;
    }

h1 {
    font-size: xx-large;
}
```
Save the changes your HTML and CSS files, and upload them to your week1 directory. Your cremebrulee.html file should now look more like this: ![Creme Brulee Page With CSS](cremebrulee2.png)

You're done!

## Due Date
You must have this exercise completed by midnight tomorrow night (11:59pm on Friday, September 1). On Saturday morning, my grader or I will go to `http://people.rit.edu/youruserid/igme230/week1`, to see if all the files are there, and if they bear some resemblance to what was required. 
