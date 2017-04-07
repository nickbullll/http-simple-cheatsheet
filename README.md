<p align="center">
  <img src="http://i.imgur.com/zsuLfiU.png" alt="http logo"/>
</p>


## Table of Contents
  1. [Informational](#1-informational)  
  2. [Successful Requests](#2-successful-requests)  
  3. [Redirects](#3-redirects)  
  4. [Client Errors](#4-client-errors)  
  5. [Server Errors](#5-server-errors)

## 1. Informational
`1xx = ℹ️`

### 100 - Continue
Server is satisfied with the initial information about the request and client can continue to forward headers.

### 101 - Switching Protocols
The server suggests switching to a protocol more suitable for the specified resource. (list of proposed protocols server indicates in the header field `Upgrade`)

### 102 - Processing
The request is accepted, but it takes a long time to process it.

## 2. Successful Requests
`2xx = ✅`

### 200 - OK 
Request was successful.

### 201 - Created  
Request was successful and something new was created based on that request.

### 202 - Accepted 
Request was received successfully, but may not be acted on immediately.

### 203 - Non-authoritative Information 
Request was successful, but information sent to the client about the response comes from a 3rd party server.

### 204 - No Content 
Request was successful, but no data is sent back.

### 205 - Reset Content	
Request from the server to reset the information sent, such as form data.

### 206 - Partial Content	
Response to a successful request for only part of a document.

## 3. Redirects
`3xx = 👉 `

### 300 - Multiple Choices
Response indicating that what was requested has moved or that there are multiple options that match the request.

### 301 - Moved Permanently	
Requested document was moved permanently and response contains the URL for that new location.
Important to use when changing domains names or	URLS of existing documents.

### 302 Found
Requested document was temporarily moved to a different location. The URL of the new location is sent  
back with the response. 303 and 307 are more specific versions at this type and were implemented as of HTTP/1.1.

### 303 See Other (HTTP/1.1)
Requested document found and responds with the URI where the document can be currently be found.

### 304 Not Modified	
Requested document has not changed since the last time it was requested. Client loads the document from the cache.

### 305 Use Proxy	
Requested document can only be accessed through a specified proxy.

### 307 Temporary Redirect (HTTP/1.1)
Requested document can temporarily found at a	different URL, which is given in the response.
This is a more pure version of what a 302 is normally meant to be.

## 4. Client Errors
`4xx = ❌`

### 400 Bad Request	
The server did not understand the request.

### 401 Unauthorized	
Client must be authorized before access, typically through some kind of login.

### 403 Forbidden
Client does not have permission to access the requested document. If this shows up on a document that should be available, it is likely a permissions issue.

### 404 Not Found	
Requested document was not found at the URL give and there is no new location specified for the document. Does not mean that the document is permanently missing from the given URL.

### 405 Method Not Allowed
Request method was not allowed for the specified document.

### 406 Not Acceptable	
Requested document cannot be sent in a way that the client can understand.

### 407 Proxy Authentication Required	
Client must be authorized by the proxy before the requested document can be sent. 

### 408 Request Timeout
Amount of time for the request exceeded the amount of time that the server is set to wait for a request.

### 409 Conflict	
Requested document could not be sent because of a conflict in the request.

### 410 Gone	
Similar to a 404, except that it means the document is permanently gone from the URL and there is no new location specified.

### 411 Length Required
Request refused because content length must be specified by client.

### 412 Precondition Failed	
At least one condition of the request has failed.

### 413 Request Entity Too Large	
Request was larger than the server was able to handle. A common example of this would be if a File is sent through a posted form and it is larger than the server settings allow tor a post.

### 414 Request URL
The URL was longer than what the server could handle. A URL resulting in this error is normally thousands of characters long, thus it is rarely an issue.

### 415 Unsupported	Media Type
Indicates that the format of at least part of the request is unsupported.

### 416 Requested Range Not Satisfiable
Request could not be fulfilled. Can occur if client requests a part of a document that doesn't exist.

### 417 Expectation	Failed
The server could not fulfill the requirements sent in the	"Expect" header field.

## 5. Server Errors
`5xx = ⛔`

### 500 - Internal Server	
Generic error message meaning that something broke but nothing more specific can be sent.

### 501 - Not Implemented
Server does not support what is required to fulfill the request.

### 502 - Bad Gateway	
Server acting as a gateway or proxy received response from an upstream server that was deemed invalid.

### 503 - Service Unavailable	
Server is currently unavailable due to high load, maintenance, or other temporary situation.

### 504 - Gateway Timeout
Server acting as a gateway or proxy did not receive response within the amount of time that the server is set to wait for a response.

### 505 - HTTP Version Not Supported		
Server does not support the HTTP protocol used by the client for the request.

## Contribution

- Report issues
- Open pull request with improvements
- Spread the word
