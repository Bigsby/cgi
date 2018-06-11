# CGI
**Common Gateway Interfaces** (CGI) are called **Web API**s, these days. In truth, they're just **HTTP Request Handler**s. We are in an API first era. Here I'll explore a plethora of alternatives to implement these applications.

# Functionality
The needed functionality for a full GCI.

1. Simple GET - Handle simple HTTP Get request of a known URL
2. Query Parameterized GET - Handle parameters in the query string
3. Route Paraneterized GET - Handle parameters in the URL path
4. Simple POST - Handle a simple HTTP request of a known URL
5. Other verbs - Handle other (than GRT and POST)
6. Catch all 404 - Handle bad request and returning other (that 200) HTTP codes
7. File Upload (to sever) - Handle file upload to server
8. File Download (to client) - "Send" file to client
9. Authorization - Handle requests that don't provide proper identification data

# HTTP
**H**yper**t**ext **T**ransfer **P**rotocol is a standard protocol defined on top of TCP/IP, being TCP/IP the actual packet transport layer handling protocol taking care of request consistency and completeness and the likes. An HTTP request looks like so:
```
METHOD /virtualpath HTTP/version
Host: httpAuthority
headerKey1: headerValue1
headerKey2: headerValue2
Content
```
Where:
- *virtualpath* is the path within the request handler, e.g., a file path
- *version* is the HTTP version, usually 1.1 or 2.0
- *httpAuthority* is the address where the handler is located, including the port seperated by a colon
-- default HTTP port is 80
-- default HTTPS port is 443
-- It can be an IP or a domain for a DNS to resolve. E.g., 127.0.0.1 (same as 127:0.0.1:80), www.example.com:8080
- Headers are metadata that help understand the request, e.g., content type and length, accepted response content types, etc.

And the HTTP response looks like so:
```
HTTP/version responseCode responseText
headerKey1: headerValue1
headerKey2: headerValue2
Content
```
Where:
- *version* is the HTTP version, usually 1.1 or 2.0
- *responseCode* is the [HTTP code](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes) that represents the result of the request.
- *responseText* is a human readable description of *responseCode*
. Headers are metadata that that help client use the request, e.g., content type and length, expiry date, etc.

That's just it.

# Alternatives
The alternatives...

|Name|Runtime|HTTP Processor|Language|IDE|
|-|-|-|-|-|
