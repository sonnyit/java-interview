Web Services 
---

List questions:

1. [What is a Web Service?](#what-is-a-web-service-)
1. [What are the advantages of Web Services?](#what-are-the-advantages-of-web-services-)
1. [What are different types of Web Services?](#what-are-different-types-of-web-services-)
1. [What is REST Web Services?](#what-is-rest-web-services-)
1. [What are advantages of REST web services?](#what-are-advantages-of-rest-web-services-)
1. [What are disadvantages of REST web services?](#what-are-disadvantages-of-rest-web-services-)
1. [What is a Resource in Restful web services?](#what-is-a-resource-in-restful-web-services-)
1. [What are different HTTP Methods supported in Restful Web Services?](#what-are-different-http-methods-supported-in-restful-web-services-)
1. [Can we maintain user session in web services?](#can-we-maintain-user-session-in-web-services-)

---

1. ##### What is a Web Service? [&#10548;](#web-services-)
	
	Web Services work on client-server model where client applications can access web services over the network. Web services provide endpoint URLs and expose methods that can be accessed over network through client programs written in java, shell script or any other different technologies.
Web services are stateless and doesn’t maintain user session like web applications.

1. ##### What are the advantages of Web Services? [&#10548;](#web-services-)

	Some of the advantages of web services are:

	- Interoperability: Web services are accessible over network and runs on HTTP/SOAP protocol and uses XML/JSON to transport data, hence it can be developed in any programming language. Web service can be written in java programming and client can be PHP and vice versa.
	- Reusability: One web service can be used by many client applications at the same time.
	- Loose Coupling: Web services client code is totally independent with server code, so we have achieved loose coupling in our application.
	- Easy to deploy and integrate, just like web applications.
	- Multiple service versions can be running at same time.

1. ##### What are different types of Web Services? [&#10548;](#web-services-)

	There are two types of web services:

	- SOAP Web Services: Runs on SOAP protocol and uses XML technology for sending data.
	- Restful Web Services: It’s an architectural style and runs on HTTP/HTTPS protocol almost all the time. REST is a stateless client-server architecture where web services are resources and can be identified by their URIs. Client applications can use HTTP GET/POST methods to invoke Restful web services.

1. ##### What is REST Web Services? [&#10548;](#web-services-)

	REST is the acronym for REpresentational State Transfer. REST is an architectural style for developing applications that can be accessed over the network. REST architectural style was brought in light by Roy Fielding in his doctoral thesis in 2000.

	REST is a stateless client-server architecture where web services are resources and can be identified by their URIs. Client applications can use HTTP GET/POST methods to invoke Restful web services. REST doesn’t specify any specific protocol to use, but in almost all cases it’s used over HTTP/HTTPS. When compared to SOAP web services, these are lightweight and doesn’t follow any standard. We can use XML, JSON, text or any other type of data for request and response.

1. ##### What are advantages of REST web services? [&#10548;](#web-services-)

	Some of the advantages of REST web services are:

	- Learning curve is easy since it works on HTTP protocol
	- Supports multiple technologies for data transfer such as text, xml, json, image etc.
	- No contract defined between server and client, so loosely coupled implementation.
	- REST is a lightweight protocol
	- REST methods can be tested easily over browser.

1. ##### What are disadvantages of REST web services? [&#10548;](#web-services-)

	Some of the disadvantages of REST are:

	- Since there is no contract defined between service and client, it has to be communicated through other means such as documentation or emails.
	- Since it works on HTTP, there can’t be asynchronous calls.
Sessions can’t be maintained.

1. ##### What is a Resource in Restful web services? [&#10548;](#web-services-)

	Resource is the fundamental concept of Restful architecture. A resource is an object with a type, relationship with other resources and methods that operate on it. Resources are identified with their URI, HTTP methods they support and request/response data type and format of data.

1. ##### What are different HTTP Methods supported in Restful Web Services? [&#10548;](#web-services-)

	Restful web services supported HTTP methods are – GET, POST, PUT, DELETE and HEAD.

1. ##### Can we maintain user session in web services? [&#10548;](#web-services-)

	Web services are stateless so we can’t maintain user sessions in web services.

References
---
1. [web services interview questions](http://www.journaldev.com/9193/web-services-interview-questions-soap-restful)
