

**Separation of concerns:**

@jokosanyang
@hrmstockdale
@baalwaan


---

<!-- >@Baalwaan -->

What is separation of concerns?

SOC is the idea that each module or layer in an application should be only responsible for one thing and should not contain code that dealth with other things.

---

Benefits of Separations of concerns

- split responsibilities between backend & frontend
- Reduces code complexity;
- Breaks large application down into smaller units;
- Makes making ammendments a lot easier

---


What is the backend ?
<!-- and what tasks are normally handled in the back end? -->

- Also known as the server side  is what receives requests from the clients, and contains the logic to send the appropriate data back to the client 
 
The backend usually consists of three parts:
1. server
2. application
3. database

---

![Process of reqest](https://i.ibb.co/2jBqqhs/Screen-Shot-2019-03-26-at-15-28-21.png);
Server is what processes our requests and delivers data to the client.
<!-- log into code academy


info sent to server, server makes sure that input is right. if everything correct

server will parse data and send it to database which checks if combinations exists.

then we will send data back to client and direct them to the profile page-->


---

## Client side vs server side:
Client side scripts are:
- downloaded, compiled and run in the browser...

Server side scripts are:
- run on a web server

---

![diagram outlining processes](https://4.bp.blogspot.com/-NE9NEo4JxTE/Vvzh85e_6OI/AAAAAAAAAu8/fjGUEWCB0DMpaVTQh006H4Vxsg0JyLu-A/s1600/proc.gif)

---

### Tasks on client side:
- flash games
- cookies
- responsive design 

### Tasks on server side:
- accessing databases
- search engines
- regularly updating content

---

### Tasks that can be done on either side:
- templating
- validation

---

- Some tasks can be implemented on either the client or the server. What are the pros and cons of running code on the client, rather than the server (and vice versa)?


---


| Client side | Server side |
| -------- | -------- |
| Scripting language (usually JS) needs to be enabled on the client computer (they can turn this off)     | Can use many languages eg Ruby, Python, PHP and Java   | 
| Very slow loading for large amounts of data | Can handle massive data, eg search engines or social networks    | 
| Cannot store data | Needed for dynamic data, eg storing user login details       | 


---


| Client side | Server side |
| -------- | -------- |
|  Mostly customises UI     | Has the ability to highly customize the response based on the user's requirements, access rights, or queries into data stores.     | 
|  Much more efficient in terms of server load     | Doesn't depend on client's computer's perfomance capacabilities as much     | 


---

 
> In the end, it's up to you. 
> Certain processes need to be done in a specific place, but mostly, it depends on the needs of your project.


---


**Alternative back-end technologies:**
> @hrmstockdale

| lang | Details | Pros |
| -------- | -------- | -------- |-------- |
| node.js| full-stack js (learning curve), async, new (content & community),  microservices architecture |async, new (content & community)  | 
| python |  1@, 2@   |big data, academia | |
| Java | concurrent, class-based, OO   | b2b security, android devices, 'write once & run everywhere'     | |
| .NET|  1@DLR |intergrates well with Microsoft OS, webapps  ||
| PHP|  less strict (not compiled)  | |
| Ruby|  reflective, OO, 1@, 2@,  | 60k libraries active community  |  |

gloss
1. @dynamic type system
    - ~~static~~, types associated at run-time ~~compile-time~~.
3. @automatic memory management
    - undefined.

**node.js**

**pros**

- asynchronous +
- non-blocking
- = Basically... it can process several simple tasks AND the main thread without blocking or choking it. 
- online gaming, chats, video conferences, or any solution that requires constantly updated data - e.g [Paypal](https://medium.com/paypal-engineering/node-js-at-paypal-4e2d1d08ce4f) reduced response time by 35% java -> node.js
- rich ecosystem - npm. A wealth of active, free packages
- open-source *and* global corporate support (IBM, Microsoft, PayPal, Fidelity and SAP)

**cons**
- single-threaded - CPU bound tasks can block the event loop and cause delays. (is it a prob outside of computation-heavy systems? 
    - e.g its really good for real-time applications with intense I/O, requiring speed and scalability.)
- asynch = callbacks(callbacks(callbacks(callbacks(callbacks(callbacks(callbacks(... you get the idea)))))));
- (again, is this a prob with node.js or with poor practise?
    - naming functions
    - modularize
    - error handling
    - see more @http://callbackhell.com/)

---

## Writing for different environments:

JavaScript is a fabulous full-stack language, but as you may have noticed, it's not exactly the same for when you're writing for Node and for browsers.

---

![require meme](https://i.imgur.com/f1tB4gW.png)


---

Node JS 
- doesn't access external files/urls
- no DOM (don’t have the document, window and all the other objects that are provided by the browser)
- uses CommonJS module system, browser uses ES Modules 
    - Node = require()
    - Browser = import

---

- provides lots of helpful "APIs" through the modules
- YOU control the environment 
    - don't need to worry about ES5/6 compatibility etc

---

#### Tools that can help:
- babel (converts ES6 to ES5 compatible)
- jsdom (creates a fake DOM in Node)


---

### Links
GoodvBad node.js
https://www.altexsoft.com/blog/engineering/the-good-and-the-bad-of-node-js-web-app-development/

https://www.upwork.com/hiring/development/a-beginners-guide-to-back-end-development/

node apis official
https://nodejs.org/docs/latest/api/index.html
