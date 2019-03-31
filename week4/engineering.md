# Engineering 
![](https://media.giphy.com/media/YRzUudROIFEic/giphy.gif)


## Modules

Good authors divide their books into chapters and sections; good programmers divide their programs into modules. 

Modules — a way to include functionality declared in one file within another. 


* Why is it a good idea to modularise your code? 

1. Code can be split into smaller files of self-contained functionality.
1. The same modules can be shared across any number of applications.
1. Ideally, modules need never be examined by another developer, because they’ve has been proven to work.
1. Code referencing a module understands it’s a dependency. If the module file is changed or moved, the problem is immediately obvious.


* What are require and module.exports? 

CommonJS specifies a simple API for declaring modules server-side. This is the format used in Node.js, which meant the Node package manager, npm, could be developed.

> module.exports (exports) and require (imports)

If you want to export multiple functions you could assign functions as methods on an object, which you then export.


---

* Why can't you use them in the browser? 

In the browser each script initiates a render-blocking HTTP request. ES6 modules are pre-parsed in order to resolve further imports before code is executed.   

CommonJS modules load dependencies on demand while executing the code. Dependency management becomes complicated, as load order matters.


---


* How might you modularise client-side code?

On the web, you can tell modern browsers (ES6) to treat a ``<script>`` element as a module by setting the type attribute to module. e.g. 

``<script type="module" src="main.mjs"></script>``

---

BUT 
* modules are evaluated only once, while classic scripts are evaluated however many times you add them to the DOM. Every script halts further processing while it’s run.
* module scripts and their dependencies are fetched with CORS. This means that any cross-origin module scripts must be served with the proper headers, such as Access-Control-Allow-Origin: *. This is not true for classic scripts.


---

## 🕓 🕝 🕘 Asynchronous functions

![dogs](https://media.giphy.com/media/hyQ8ESUyePo2s/giphy.gif)

---

When you execute something **synchronously**, you wait for it to finish before moving on to another task. When you execute something **asynchronously**, you can move on to another task before it finishes.

---

**How do I write asynchronous functions for Node?** Write normal functions, the only difference is that they are not executed immediately but passed around as callbacks.

---

Functions that can take other functions as arguments are called **higher-order functions**.

```
const numbers = [2,4,1,5,4]

function isBiggerThanTwo (num) {
  return num > 2
}

numbers.filter(isBiggerThanTwo)
```

***Why should you use asyncronous forms of functions wherever possible in Node?***

To avoid blocking the main threat.

**📞*What are error-first callbacks, and why is it important to follow that pattern in your own code?***

-- Most asynchronous methods in Node.js follow a pattern referred to as an **error-first callback**. 
-- With this pattern, a callback function is passed to the method as an argument.
-- When the operation either completes or an error is raised, the callback function is called with the Error object (if any) passed as the first argument. If no error was raised, the first argument will be passed as null.


```
const fs = require('fs')
fs.readFile('file.md', 'utf-8', function (err, content) {
  if (err) {
    return console.log(err)
  }

  console.log(content)
})
```

***Why should you avoid using throw in callbacks?***

```
// THIS WILL NOT WORK:
const fs = require('fs');

try {
  fs.readFile('/some/file/that/does-not-exist', (err, data) => {
    // Mistaken assumption: throwing here...
    if (err) {
      throw err;
    }
  });
} catch (err) {
  // This will not catch the throw!
  console.error(err);
}
```

- `throw` delivers an error synchronously — that is, in the same context where the function was called.
- Callbacks are the most basic way of delivering an error asynchronously. The user passes you a function (the callback), and you invoke it sometime later when the asynchronous operation completes. The usual pattern is that the callback is invoked as callback(err, result), where only one of err and result is non-null, depending on whether the operation succeeded or failed.

***When might you use the synchronous form of a function instead?***

## Input/output
### (shake it all aboutput)

![](https://media.giphy.com/media/DEYOQQapldeiA/giphy.gif)

The fs, or file system module, allows us to access and manipulate files and directories. 

The path module is for manipulating file paths - which we might then use to access files in fs. 

They are both default modules in Node (but they still need importing).

![](https://media.giphy.com/media/w48WeMIN73QsM/giphy.gif)

The fs module contains functions for manipulating files such as:

```
fs.readFile()
fs.mkdir()
fs.open()
fs.stat()
```

![](https://i.imgur.com/MZqLmKQ.png)

![](https://media.giphy.com/media/MSt2969hVfGJW/giphy.gif)


Fs relies on using paths. Paths are sometimes relative to the directory we are in, rather than absolute. They may also change several times during development.

For this reason we use the path module (rather than just strings).

`_filename` provides the absolute path to the file that is currently executing.

`_dirname` provides the absolute path to the working directory where the file being executed is located.

![](https://media.giphy.com/media/iGUTUvreEawwg/giphy.gif)

The path module also contains functions for manipulating file paths such as:

```
path.join()
path.basename()
path.extname()
path.relative()
path.parse()
```

![](https://i.imgur.com/XugApRo.png)


## Working with URLs

* What is a urlObject and how is it structured? 

```JavaScript

const http = require('http'),
      url = require('url'),
 
makeServer = function (request,response){
   let path = url.parse(request.url).pathname;
   console.log(path);
   if(path === '/'){
      response.writeHead(200,{'Content-Type':'text/plain'});
      response.write('Hello world');
   }
   else if(path === '/about'){
     response.writeHead(200,{'Content-Type':'text/plain'});
     response.write('About page');
   }
   else if(path === '/blog'){
     response.writeHead(200,{'Content-Type':'text/plain'});
     response.write('Blog page');
   }
   else{
     response.writeHead(404,{'Content-Type':'text/plain'});
     response.write('Error page');
   }
   response.end();
 },
server = http.createServer(makeServer);
server.listen(3000,()=>{
 console.log('Node server created at port 3000');
});


The URL module provides us with an easy way to work with urls.


> "A URL *string* is a structured string containing multiple meaningful components. When parsed, a URL *object* is returned containing properties for each of these components." 
> 


![](https://i.imgur.com/OXRhorT.png)


# Examples 

```JavaScript
const queryString = require('query-string');
 
console.log(location.search);
//=> '?foo=bar'
 
const parsed = queryString.parse(location.search);
console.log(parsed);
//=> {foo: 'bar'}
 
console.log(location.hash);
//=> '#token=bada55cafe'
 
const parsedHash = queryString.parse(location.hash);
console.log(parsedHash);
//=> {token: 'bada55cafe'}
```

* Why is it important to be able to turn JavaScript objects into querystrings and back again? 

Like that of post requests a query string can be the result of your own client system, but the client system can also be bypassed. In other words a query string is a potential entry point with respect to a certain type of hacking. I have not taken the time to work out an actual example, but for now I will just say that it is important to be aware of how the object that is parsed from the query string is being used.


<iframe src="https://giphy.com/embed/4Zo41lhzKt6iZ8xff9" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/4Zo41lhzKt6iZ8xff9"></a></p>

<iframe src="https://giphy.com/embed/21Pi5sBUXvY62KrrHA" width="480" height="480" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/cute-aww-eyebleach-21Pi5sBUXvY62KrrHA"></a></p>


### Resources:

#### Asynchronous: 
https://nodejs.org/api/errors.html#errors_error_first_callbacks
https://www.joyent.com/node-js/production/design/errors
https://stackoverflow.com/questions/40511513/why-does-node-prefer-error-first-callback
https://nodejs.org/api/errors.html#errors_error_first_callbacks
https://blog.risingstack.com/node-hero-async-programming-in-node-js/
https://stackoverflow.com/questions/748175/asynchronous-vs-synchronous-execution-what-does-it-really-mean
https://stackoverflow.com/questions/6898779/how-to-write-asynchronous-functions-for-node-js

--- 

![](https://media.giphy.com/media/TGLLaCKWwxUVq/giphy.gif)
