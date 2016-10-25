Java Servlets
---

1. [What is different between web server and application server?](#what-is-different-between-web-server-and-application-server-)
1. [Which HTTP method is non-idempotent?](#which-http-method-is-non-idempotent-)
1. [What is the difference between GET and POST method?](#what-is-the-difference-between-get-and-post-method-)

---

1. ##### What is different between web server and application server? [&#10548;](#java-servlets-)

	short answer: web server serves static content, application server serves dynamic content.
	
	long answer:
	
	A web server responsibility is to handler HTTP requests from client browsers and respond with HTML response. A web server understands HTTP language and runs on HTTP protocol.
Apache Web Server is kind of a web server and then we have specific containers that can execute servlets and JSPs known as servlet container, for example Tomcat.
	
	Application Servers provide additional features such as Enterprise JavaBeans support, JMS Messaging support, Transaction Management etc. So we can say that Application server is a web server with additional functionalities to help developers with enterprise applications.

1. ##### Which HTTP method is non-idempotent? [&#10548;](#java-servlets-)

	A HTTP method is said to be idempotent if it returns the same result every time. HTTP methods GET, PUT, DELETE, HEAD, and OPTIONS are idempotent method and we should implement our application to make sure these methods always return same result. HTTP method POST is non-idempotent method and we should use post method when implementing something that changes with every request.

	For example, to access an HTML page or image, we should use GET because it will always return the same object but if we have to save customer information to database, we should use POST method. Idempotent methods are also known as safe methods and we don’t care about the repetitive request from the client for safe methods.

1. ##### What is the difference between GET and POST method? [&#10548;](#java-servlets-)

	- GET is a safe method (idempotent) where POST is non-idempotent method.
	- We can send limited data with GET method and it’s sent in the header request URL whereas we can send large amount of data with POST because it’s part of the body.
	- GET method is not secure because data is exposed in the URL and we can easily bookmark it and send similar request again, POST is secure because data is sent in request body and we can’t bookmark it.
	- GET is the default HTTP method whereas we need to specify method as POST to send request with POST method.
	- Hyperlinks in a page uses GET method.



