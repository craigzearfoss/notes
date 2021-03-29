# Stateless vs. Stateful
---
### Stateless
- Pass a token (which gets authenticated on each request)
- The token is stored on back end in a database or cache.
- Scales well but may make extra calls to the database.
- Usually caching is done to reduce database calls.
- The application has no state so if a server goes down you just can redirect to another server.
- You can easily add new servers

### Stateful
- Login information is saved on the server in a session or other way
	- Server sends a key to the browser which is passed and verified by the server on subsequent requests
- If the server goes down the session goes down and the user will usually be logged out.
- We can say that the application has the state.
- Only one call to the database on logging. None on subsequent requests.
- Less database requests than stateless.
- If you are using multiple servers they will have to share sessions to share the key.

