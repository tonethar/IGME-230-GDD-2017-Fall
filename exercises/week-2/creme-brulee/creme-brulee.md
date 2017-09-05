# Basic HTML & CSS Exercise 

## Overview & Goals

In today's exercise, we will be taking a text document, marking it up as an HTML document, adding basic CSS formatting, and uploading it to your RIT web space. 

We will also be adding a configuration file to your RIT web space to override some of the server's (problematic) default behavior.

## Setting Up Your Folders and Files

In your local 230 folder (which we already created together), create folder called exercises. In there, create a folder called ICE2A. 

I've put uploaded a file called [cremebrulee.txt](cremebrulee.txt) to Github. When you click the link to view that file on Github, you'll see that it's a plain text file into which I've copied and pasted the content from the [Wikipedia entry for "Crème brûlée"](https://en.wikipedia.org/wiki/Cr%C3%A8me_br%C3%BBl%C3%A9e). 

To download that text file to your computer for editing, right-click on the button in the top right corner of the file that says "Raw," choose "Save link as...", and save the file to the week1 folder you just created.

You're also going to need to download the two images: [2014_0531_Crème_brûlée_Doi_Mae_Salong.jpg](2014_0531_Crème_brûlée_Doi_Mae_Salong.jpg) and [225px-Crema_Catalana_El_Glop.jpg](225px-Crema_Catalana_El_Glop.jpg). For each of those files, you will see a Download button in the top right corner. Right-click that button, choose "Save link as...", and download it to your local week1 folder. Then epeat that process with the second image, . 

## Marking Up a Text File

Open the cremebrulee.txt file in your text editor of choice (I recommend Brackets, though Visual Studio Code has some cool features we'll reference below). It currently has no HTML markup at all--you're going to turn it into a proper HTML document, and add some simple CSS rules to make it look a bit more like the original Wikipedia entry. 

Use File->Save As... to save a new copy of the file called cremebrulee.html. Make sure you save it to the ICE2A folder and give it an .html extension--it's the extension that tells your editor to enable its HTML support. 

There are a lot of accented and foreign characters in this document. In HTML 4, the default character encoding for files was ISO-8859-1, which doesn't properly display special characters (like smart quotes and diacritical marks). Those characters had to be escaped out (e.g. &eacute; had to be represented as `&eacute;`, &copy; had to be represented as `&copy;`, and & had to be represented as `&amp;`)--if you didn't do that, they didn't display properly in the browser. HTML 5 uses UTF-8 encoding, which allows those special characters to appear properly in your document.

Because this Wikipedia article has many non-standard characters (like "smart" quotes and diacritical marks), the UTF-8 encoding is very helpful. 

First, set up your document with the standard HTML5 "skeleton":

```<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title></title>
</head>
<body>

</body>
</html>
```

Now we need to mark the text up as HTML. (Use the actual wikipedia page as a refrerence.)

- Add an h1 heading for the page title, and h2 headings for all of the subsections.
- Add paragraph tags to the individual paragraphs of text. 
- Make the Contents and References sections into numbered ("ordered") lists, and the See Also, Bibliography, and External Links sections into bulleted ("unordered") lists. (Hint: Emmet can be very helpful with this, too!)
- Add the two images where indicated in the file, with appropriate alt text. Don't worry about positioning them for now; we'll deal with that when we add the CSS. 
- Use the `<sup>` tag to make each of the footnote references a superscript.
- Where appropriate, add tags to make text bold (`<strong>...</strong>`) and/or italicized (`<em>...</em>`).

Don't worry about adding links yet; we'll be doing that next week. 

When you're done, preview your document in your editor or browser. It should look something like this: ![Creme Brulee Page Without CSS](cremebrulee1.png)

## Publishing Your Files
 
Once you're satisfied with the HTML file, you're going to upload your exercises folder (which includes your ICE2A folder and its contents) to your 230 folder on Banjo. 

Test it by going to `http://people.rit.edu/yourid/230/exercises/ICE2A` -- you should see the .txt and .html files, and the two images. Click on the html file and make sure it displays properly. If you run into problems here, **ask for help ASAP**. 

## Adding Basic CSS Formatting
Now we're going to use CSS to start to make the page look a bit more like the original Wikipedia entry.

Create a new file in the ICE2A folder called cremebrulee.css. Add a link to the stylesheet in your <head> by typing `<link rel="stylesheet" type="text/css" href="cremebrulee.css" />`. 

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
Save the changes your HTML and CSS files, and upload them to your ICE2A directory. Your cremebrulee.html file should now look more like this: ![Creme Brulee Page With CSS](cremebrulee2.png)

You're done!

## Due Date
This is due before the start of our next class. There's no need to send us a link or post anything to GitHub for this; as long as you have it in the right location, we can find it from our class list links.
