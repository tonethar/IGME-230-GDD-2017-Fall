# Week 2A - Review of HTML

## Topics
- HTML Basics
- Structural and semantic tags
- Paths
- HTML validation

## The layers of Web design
   1. Content
   1. Structure
   1. Presentation
   1. Behavior

## Review and Demo
Together, we'll build a Web page, reviewing the following:
- Basic markup and structure
- Structural and semantic elements
   - Structural markup is using to encode information about the structure of a document. Examples: `<heading>, <footer>, <div>, and <span>`. Structural markup such as `<div>` delineates major sections of the document and are also block-level elements that sit on their own line. 
   - Semantic markup means using tags that add meaning to the content. Examples: `<cite>, <quot>, <ul>, <ol>, <em>`. Semantic markup such as `<cite>` adds extra information without altering the structure of a document, and may be either inline or block elements.
- HTML5 structural tags enhance our structure and give us more to work with later on:
   - `<header>, <main>, <nav>, <aside>, <figure>, <footer>`, etc.
   - https://www.w3schools.com/html/html5_new_elements.asp
- *Container* tags describe content contained within them. Ex: `<p>, <a>, <span>, <div>`
- *Standalone* tags describe no additional information. Ex: `<img>, <link>`
- Tags to know:
   - h1, h2, etc.
   - p
   - a
   - ul, ol, li
   - img
   - comments: `<!-- This is a comment. -->`
- Paths for linking between pages and other resources
``` 
<a href=“bio.html”>Bio Page</a>
<a href=“proj/p1/proj1.html”>P1</a>
<a href=“../../index.html”>P1</a>
```
   - Don’t start a path with / (This goes to the root, usually WAY above your user account)
   - Remember rules for filenames in your paths:
   -- No spaces
   -- No special characters (?, !, *, etc.)
   -- Avoid caps (case-sensitive)

## Note on using images
Images should always be integrated into your page at their native resolution. Resizing via HTML or CSS causes long load times and uses up unnecessary space on our server, and also leads to distortion.
See our in-class demo for a refresher on proper image optimization.

## HTML Skeleton
This is the bare minimum needed for a valid HTML document:

```
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="utf-8" />
	<title></title>
</head>
<body>

</body>
</html>
```

## Validation
https://validator.w3.org/

## Exercises
- [Basic Markup](../exercises/ICE2A/2A_ICE-basicMarkup.md)
- [230 Home Page](../exercises/2A_230-home-page.md)
