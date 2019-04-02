# Make a request from the server
---
### What npm modules are available 
---
1. HTTP
    - Is our default module, we can plug and go without having to install any dependencies
    - functionality is fairly low-level, you're required to receive data in chunks rather than providing a callback funtion to be executed when the data is received, then you till need to parse the response data manually
    - This module does not support 'https', so we need to require the 'http' module if the API were using communicates over 'HTTPS'
    - may take more effort to get the data you want but is great if you dont want to add too many dependencies 

---

2. Request
    - The peoples choice when using Node.js
    - More friendly than the default 'http' module and is considered the go-to module of choice
    - Unlike the 'http' module you have to install this one as a dependency from npm 

---

#### What is a Promise?
- A promise represents the result of an asynchronous operation and is in one of three different states:
        - pending - The initial state of a promise
        - fulfilled - The state of a promise representing a successful operation
        - rejected - The state of a promise representing a failed operation


---
3. Axios
    - Need to install a dependency 
    - Is a Promise based HTTP client for the browser as well as node. 
    - Using promises is a great advantage when writing asyncronous code, as it can get confusing.
    - Axios parses JSON resonses by default - rather convenient
    - Error handing can also be done with catch() as promises is being used.
---

4. SuperAgent
    - Need to install a dependency 
    - Similar to Axios, SuperAgent is used for making AJAX requests in the browser but works in Node.js as well.
    
    - What's cool about SuperAgent is that you have other useful functions that you can chain onto requests such as query() to add parameters to the request.

    

