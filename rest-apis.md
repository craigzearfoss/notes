# REST APIs
---
### REST stands for Representational State Transfer
- Server sends you a representation of resouces.
- Representation is usually in JSON. 
- It is decoupled from what is stored on the back end. (The back end can be stored in any format.)
- **stateless* protocol
	- No state information is stored on the host server.
	- The client owns the state.
	- Don't store information in memory on the server and rely on it being there.
	- Some state information can be stored int other places like databases
	- Disadvantages
		- Usually slower.
		- Has a higher payload.
		- If browser crashes you lose state.
		- Need to make sure server and client versions are compatible.
	- Advantages
		- Scales well.
		- If server crashes you can easily connect to a different server.
		- Separation of concern.
			- Changes made on server won't affect state.
			- You can add intermediate gateways and proxies with no problems.

### REST Constraints
- Client/Server
- Statelessness
- Cacheability
- Layer Systems
- Uniform Interface (HATEOS)
	- hypermedia as the engine of application state
	- Each endpoint returns a specific set of data.
	- It can get "chatty" because of all of the round trips to get data.
	- Facebook created GraphQL to get around this by being able to request specific from a single endpoint.

### State Transfer in REST
- REST is stateless so we do not sttore anything on the server.
- We have to transfer as much information to the the server as possible.
- Slower than stateless because you need to rebuild the state on the server on each request.
- Heavier payload than stateless because you have to pass the state on each request.

### REQUEST
- The request is made to a URL (universal resource locator) for a resource, or resources.
- The server returns the representation of resources in response.
- The response representation can be HTML, IMAGE, XML,JSON, etc.
- A URL has three parts.  For example: http://www.mysite.com/img/flowers.jpg
	- protocol - https
	- host - www.mysite.com
	- resource - img/flowers/lily.jpg
- A REQUEST has a url plus a verb.
- Verbs desribe the action that we are requesting of the server and include:
	- GET - request for a resource, like a web page
	- POST - submiting information to the server
	- PUT
	- DELTETE
	- etc.

#### REQUEST API Example
- REQUEST:
	- https://api/flickr.com/services/rest?method=flickr.photos.getinfo&photo_id=207935948
		- REST API endpoint URL - https://api/flickr.com/
		- METHOD - flickr.photos.getinfo
		- PARAMETERS - photo_id=207935948
- RESPONSE:
	- Can be in multiple formats, including REST, XML-RPC, SOAP, JSON, Serialized PHP, etc.

### REST API call example:
- Run from Chrome developer tools.
```
fetch("https://api.github.com").then(a=>a.json()).then(console.log)
```

### Google (Apigee) 
	- Cross-cloud API management platform
	- [https://cloud.google.com/apigee/](https://cloud.google.com/apigee/)	


