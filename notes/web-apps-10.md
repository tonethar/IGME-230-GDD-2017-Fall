# 10 - Web Services

## I. Overview
Reading and writing data to and from the Internet, whether to/from your own server, or by working with a cloud service like Firebase, is a BIG topic.

In this course, we are just going to scratch the surface and work with the "read only" web, in this case, by utilizing a web service to search for and display animated GIFs.

## II. What is a Web Service?

- A *Web Service* (http://en.wikipedia.org/wiki/Web_service) is a method of communication between two electronic devices over World Wide Web. A Web service is a software function provided at a network address over the web or the cloud; it is a service that is "always on" ...

- Web services (aka Web APIs) can be used to return informations such as the weather, mapping, nearby restaurants and other place information, photos & videos and so on. There are also services that let the developer store user data in "the cloud" where it will be available from any machine the user logs into (Google's Firebase is one such service). 

- Some examples of web services can be found on this page: [sample-web-services.md](../projects/_supporting-files/sample-web-services.md)


## III. How do we download the data?

- What we want to do is this -> to take a user request, and update part of the page (asynchronously) by exchanging small amounts of data with a server behind the scenes, without having to reload the whole page.
- The above concept is called in the web world by this term *Ajax* - https://en.wikipedia.org/wiki/Ajax_(programming)
- **Ajax** was derived from an earlier acronym *AJAX*, which stood for **A**synchronous **J**avaScript **A**nd **X**ML. The acronym fell out of favor because we now commonly retrieve other data formats besides XML.  

In this class we will simplify the process of retrieving remote data by using the `jQuery.ajax` method of the jQuery library. This method will work well cross-platform, and abstracts away the details of what's happening.

Behind the scenes, the actual browser APIS and being used by jQuery include these:

- `XMLHttpRequest` (XHR) - https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest
- `Fetch` API - https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API
- Cross-Origin Resource Sharing (CORS) - https://developer.mozilla.org/en-US/docs/Web/HTTP/CORS
- Cross-site scripting (XSS) can be used to generate &lt;script> tags and download JSON data on the fly - https://en.wikipedia.org/wiki/Cross-site_scripting


## IV. What are the data formats?
- In the early days of Ajax, XML formats such as SOAP and RSS were popular.
- More recently, JSON (**J**ava**S**cript **O**bject **N**otation) has become the format of choice because it gives smaller file sizes than equivalent XML, and is easier for web browsers to parse because it maps directly to core JavaScript data types.
- You can read about JSON here: http://www.json.org and here: 
- The 6 core data types of JSON are:
    - `String`
    - `Number`
    - `Object` (JSON object, no methods allowed!)
    - `Array`
    - `Boolean` (`true` or `false`)
    - `null`


## V. Do the exercise!
The best way to see how Ajax and Web APIs work is to build a fulling functioning example - if you haven't done so yet, go ahead and build GIF Finder, which utilizes the Giphy Web Service:

- [HW-gif-finder.md](./HW-gif-finder.md)




**[Previous Section <- WebStorage (part 9)](web-apps-9.md)**
