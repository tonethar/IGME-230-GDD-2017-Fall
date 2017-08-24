# HTTP Protocol Demo 

1. Launch the PuTTY Application (or Terminal on a Mac)

2. Type `telnet www.rit.edu 80`and press return.

Trying 129.21.1.40...

Connected to web01www01.rit.edu.

Escape character is '^]'.

3. Type `GET / HTTP/1.1` and press return.

4. Type `host: www.rit.edu`

Now you should get the RIT home page (just the HTML) back from the server:

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

<!DOCTYPE html>
<html lang="en">
<head>
<meta http-equiv="X-UA-Compatible" content="IE=edge">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<!-- The above 2 meta tags *must* come first in the head; any other head content must come *after* these tags -->
<!-- Fonts and Stylesheets -->
<link rel="stylesheet" href="//fonts.googleapis.com/css?family=Source+Sans+Pro:300,300italic,400,600,900" type="text/css">
<link rel="stylesheet" ...>
<link rel="shortcut icon" href="/_assets/images/favicon.ico">
<title>Rochester Institute of Technology</title>
<meta name="twitter:widgets:link-color" content="#F36E21">
```
