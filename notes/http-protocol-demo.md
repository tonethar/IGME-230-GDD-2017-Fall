# HTTP Protocol Demo 
The Hypertext Transfer Protocol (HTTP) is an application protocol for distributed, collaborative, and hypermedia information systems.[1] HTTP is the foundation of data communication for the World Wide Web.

https://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol

Let's use the command line to connect to RIT's web server and request the default RIT home page (this is what web browsers do).

**Try this!**

1. Launch the PuTTY Application (or Terminal on a Mac)

2. Type `telnet www.rit.edu 80`and press return.

Trying 129.21.1.40...

Connected to web01www01.rit.edu.

Escape character is '^]'.

3. Type `GET / HTTP/1.1` and press return. (**GET** is a *HTTP Request Method*)

4. Type `HOST: www.rit.edu` and press return. (**HOST** is a *HTTP Request Header*. Here we are sending just one header, but you can easily end more headers, one to a line.)

5. Press return again. (In the HTTP request protocol, a blank line indicates that there are no more request headers)

Now you should first get the *HTTP Status Code* and  *HTTP Response Headers* back from the web server.

```
HTTP/1.1 200 OK
Date: Thu, 24 Aug 2017 18:45:27 GMT
Server: Apache
Vary: Host,Accept-Encoding
X-Mod-Pagespeed: 1.12.34.2-0
Cache-Control: max-age=0, no-cache, s-maxage=10
Content-Length: 77715
Connection: close
Content-Type: text/html; charset=utf-8
```

Note that the **200** status code means everything is OK.
We also got 9 response headers back from the web server.

https://en.wikipedia.org/wiki/List_of_HTTP_header_fields

https://en.wikipedia.org/wiki/List_of_HTTP_status_codes

**Right after the status code and response headers, you will also see the actual RIT home page HTML:**

```
<!DOCTYPE html>
<html lang="en">
<head>
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Source+Sans+Pro:300,300italic,400,600,900" type="text/css">
<link rel="stylesheet" ...>
<link rel="shortcut icon" href="/_assets/images/favicon.ico">
<title>Rochester Institute of Technology</title>
<meta name="twitter:widgets:link-color" content="#F36E21">
...
<html>
<body>
.. and so on ...
</body
</html>
```
