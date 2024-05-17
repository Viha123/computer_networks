#computerNetworks #web 
- HTTP: hyper test transfer protocol
- **HTTP uses TCP**:
	- HTTP messages (application layer protocol messages) exchanged between browser (HTTP client) and Web server (HTTP server)
- HTTP is "stateless":
	- server maintains no information about past client requests
- 2 types of HTTP connections:
	- **Non-persistent, and persistent** TCP connections
### Non Persistent:
- each request response pair sent over different TCP connections
- HTTP 1.0 employs non-persistent TCP connections
- TCP buffers must be allocated, and TCP variables must be kept in both client and server, this can place a significant burden on the web server
### Persistent:
- each request response pair sent over the same TCP connections
- requests and responses between the same client and server are done over the same tcp connection in http/1.1
	- entire web page or multiple web pages residing on the same server can be sent to the same client with the same TCP connection
- HTTP server closes a connection after it has not been used for a certain time
- what does curl do: analogous to a GET request
- In the context of the web we use *browser* and *client* interchangeably
HEAD method:
- requests headers only that would be returned if specified URL were requested with an HTTP GET method
### Maintaining User/server state: cookies
- HTTP/GET response is **stateless**
	- the server sends requested files to clients without storing any state information about the client. If a client asks twice the same info, the server isn't going to say that it just sent the same thing. Its just going to serve the object again, because it does not remember that information.
	
- cookies are stored on client
- [[HTTP Cookies]]
- all HTTP requests are independent of each other
- Web sites and client browser use cookies to maintain some state between transactions
- four components:
	1. cookie header line of HTTP response message
	2. cookie header line in next HTTP request message
	3. cookie file kept on user’s host, managed by user’s browser
	4. back-end database at Web site
- http only
- cookies can be used for authorization, shopping carts, recommendations, user session states
### Web caches:
- also called **proxy server** is a network entity that satisfies HTTP requests on the behalf of an origin Web server
- ![[Pasted image 20240212124054.png]]
- user configures browser to point to Web cache
- forward proxy, reverse proxy, CDN, nginx, 
- browser sends all HTTP requests to cache
	- if object in cache: cache returns object to client
	- else cache requests object from origin server 

- What is **cache**?
- **Conditional GET**:
### HTTP 2 features:
- prevent HOL blocking by dividing data into frames
- respond with multiple things after a request (server pushing)

