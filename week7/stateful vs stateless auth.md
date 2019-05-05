# Stateful vs stateless authentication

![](https://media.giphy.com/media/12OIWdzFhisgww/giphy.gif)

---

## What is session based authentication (stateful) vs token based authentication (stateless)?

---

**session based authentication = stateful**
**token based authentication = stateless**

![](https://i.imgur.com/a7One3t.jpg)

---

### Session based (stateful) authentication:
- user state is stored on the server’s memory
- the server creates and stores the session data in the server memory when the user logs in and then stores the session Id in a cookie on the user browser
- the session Id is then sent on subsequent requests to the server and the server compares it with the stored session data and proceeds to process the requested action

---

### Token based (stateless) authentication:
- user state is stored on the client
- user data is encrypted into a JWT (JSON Web Token) with a secret and then sent back to the client
- the JWT is then stored on the client side and **sent as a header for every subsequent request**
- the server receives and validates the JWT before proceeding to send a response to the client

---

Both methods can be used together to create a hybrid system 

---

## Flow diagrams

---

### Stateful
![](https://i.imgur.com/npVNFSJ.png)

---

### Stateless
![](https://i.imgur.com/WZ690XT.png)

---

## What are the advantages and disadvantages of each?

---

| Stateful | Stateless | 
| -------- | -------- | 
| - user state stored on the server    | - user state stored on the client     | 
| - uses server memory which might create an issue when a large number of users use the app at once    | - scales better     |
|Revoke the session anytime from the server side.| Reduce session expiration problems |

<!-- First and foremost, when you have to reference a state, you’re opening yourself up to a lot of incomplete sessions and transactions. Let’s say you make a call to present a piece of data. In a stateful system where the state is determined by the client, how long is the system supposed to leave this connection open? How do we verify if the client has crashed or disconnected? How do we track the actions of the user while maintaining the ability to document changes and roll back when necessary? -->


---

![](https://media.giphy.com/media/3xz2BCohVTd7h2Kvfi/giphy.gif)

---

## Helpful reading

- https://github.com/facg3/Stateless-vs-stateful-authentication
- https://dev.to/thecodearcher/what-really-is-the-difference-between-session-and-token-based-authentication-2o39
- https://medium.com/@sherryhsu/session-vs-token-based-authentication-11a6c5ac45e4

