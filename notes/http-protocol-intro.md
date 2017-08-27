# HTTP Protocol Intro

## What is a Web Server?
A *web server* is a computer system that processes requests via HTTP, the basic network protocol used to distribute information on the World Wide Web. The term can refer to the entire system, or specifically to the software that accepts and supervises the HTTP requests.

+ https://en.wikipedia.org/wiki/Web_server

You should already be familar with RIT's "banjo" server, which hosts files for http://people.rit.edu

## The HTTP Protocol
HTTP is a *protocol* (a system of rules e.g. steps) which allows the fetching of resources, such as HTML documents. It is the foundation of any data exchange on the Web and a *client-server* protocol, which means requests are initiated by the recipient, usually the Web browser. 

A complete document is reconstructed from the different sub-documents fetched, for instance text, layout description, images, videos, scripts, and more.

+ https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview

## Discussion
- HTTP is simple and human readable. You will see this is so in our HTTP Protocol Demo today.
- HTTP can control *cacheing* (of web pages for example), *authentication* (is someone allowed to view a file or folder?), *sessions* (is this the same person that logged in 5 minutes ago?), and *redirection* (sending a browser to another location iof a file has moved)

## Review Questions
Based on your reading of the Mozilla HTTP article linked above, you should be able to answer these questions:

1. *Clients* make requests to *servers*.  Give an example of a typical HTTP *client*.
1. Give additional examples of HTTP clients.
1. Between the Web browser and the server, numerous computers and machines relay the HTTP messages. Many of these operate at a lower  layer in the (TCP/IP "stack")[https://en.wikipedia.org/wiki/Internet_protocol_suite] and are thus invisible to the client. What are these computers and machines called?
1. HTTP *requests* consist of the following:
  - an HTTP *method* such as ....
  - the path of the desired ....
  - the *version* of the ....
  - optional *headers* that ....
  - optionally a message *body* which could (for example) be an image to be uploaded
5. HTTP *responses* consist of the following:
  - The version of the HTTP protocol they follow
  - A .... , indicating if the request has been successful, or not, and why.
  - A ....
  - HTTP *headers*, like those for requests.
  - Optionally, a message *body* containing the fetched resource (ex. an HTML file).
  
Now check out the [http-protocol-demo.md](http-protocol-demo.md) page and walk through our demo of the HTTP Protocol
