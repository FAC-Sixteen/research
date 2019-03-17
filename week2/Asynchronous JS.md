# Asynchronous JavaScript

![](https://media.giphy.com/media/ikXcqqlSNH2Mw/200w_d.gif)

### by The A-Team:
#### Bobby, Banna, Joko and James

---

## What are first class functions, and higher order functions?

![](https://media.giphy.com/media/12ETcAyWE6TjHy/giphy.gif)

---

# First-class functions

![](https://media.giphy.com/media/l1J9DlCFh2h90HrnW/source.gif)

---

Functions that are treated like any other variable.

![](https://media.giphy.com/media/5VKbvrjxpVJCM/giphy.gif)

---

# Features

![](https://media.giphy.com/media/xHMIDAy1qkzNS/giphy.gif)

---

1. Can be stored in a variable, object, or array.

3. Passed as an argument to another function.

---

Can be stored in 3 ways:

1. Store in a variable: 
```
let fn = function doSomething() {};
```

2. Store in an object: 
```
let obj = { doSomething : function(){} };
```

3. Store in an array: 
```
arr.push(function doSomething(){})
```

---

## Example

```
const foo = function() { console.log("foobar"); }
Invoke it using the variable
foo();
```

---

# Higher-Order Functions

![](https://media.giphy.com/media/l1J9DlCFh2h90HrnW/source.gif)

---

This is a fancy word for a function that accepts another function as an argument.
e.g. filter, map and reduce.

![](https://media.giphy.com/media/14vFOciTnQjnl6/giphy.gif)

---

# Features

![](https://media.giphy.com/media/ZiHVfHBpoULkc/giphy.gif)

---

1. It’s first-class.
2. Takes a function as an argument.

---

## Example


```
function sayHello() {
   return function() {
      console.log("Hello!");
   }
}
```

---

# True or False Question

![](https://media.giphy.com/media/1xOOtkRkI9HO1OWcDy/source.mp4)

---

## What type of functions does this code contain? 

### Higher-order or first-class, neither or both?

![](https://media.giphy.com/media/V3Qkln2W5lFZK/giphy.gif)

---

```
const isEven = (num) => num % 2 === 0;

result = [1, 2, 3, 4].filter(isEven);

console.log(result); // [2, 4]
```

---

Answer: isEven is a first-class function and filter is a higher-order function!

![](https://media.giphy.com/media/2Fih5ShfqVr5C/giphy.gif)

---

## What is the call stack?

A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to **keep track of its place** in a script that calls multiple functions — what function is **currently being run** and what functions are **called from within** that function, etc.

---

![example](https://i.imgur.com/ZrLwWtB.png)

---

## Asynchronous Functions and Blocking Code

> "JavaScript is a synchronous programming language. But thanks to **callback functions** we can make it function like Asynchronous programming language."
> 
> -- <cite>Benjamin Franklin</cite>

---


## What Is An Asynchronous Function?

Asynchronous functions are functions that do not block the execution of subsequent code.


---


## Example of Synchronous Code

```
// Say "Hello."
console.log("Hello!");

// Say "How are you?"
console.log("How are you?");

// Say "Goodbye!"
console.log("Goodbye.");

```

---



### Result

```
1. Hello!
2. How are you?
3. Goodbye.

```

---


## Example of Asynchronous Code

```
// Say "Hello!"
console.log("Hello!");

// Say "Goodbye" two seconds from now.
setTimeout(function() {
  console.log("Goodbye.");
}, 2000);

// Say "How are you?"
console.log("How are you?");

```

---


### Result

```
1. Hello!
2. How are you?

[2 seconds later...]

3. Goodbye.

```

---


## Three ways to write asynchronous code:

- Callback functions (good)
- Promises and generators (better)
- Async/await (best. New to ES6)

---

## Callback functions ##

![](https://media.giphy.com/media/MdQOWF5kCSl7a/giphy.gif)

---

A callback is a function that is to be executed after another function has finished executing — hence the name ‘call back’. Any function that is passed as an argument is called a callback function.

Callbacks are a way to make sure certain code doesn’t execute until other code has already finished execution.

---

```
function doHomework(subject) {
  alert(Starting my ${subject} homework.);
}
```

 ```
doHomework('math');
// Alerts: Starting my math homework.
```


```
function doHomework(subject, callback) {
  alert('Starting my ${subject} homework.');
  callback();
}
```

```
function finishedHomework(){
 alert('Finished my homework')
}
```

```
doHomework('math', finishedHomework);
// Alerts: Starting my math homework.
// Alerts: Finshed my homework.
```

---

addEventListener is an in built function in JS. This event handler accepts 2 arguments, one of which is a function, which will be called when the event is triggered:

 ```
document.getElementById('button').addEventListener('click', function(){ 
 // which runs when button is clicked
 }) 
```


```
function clicked(){
 //code which runs when the button is clicked
}
```

```
document.getElementById('button').addEventListener('click', clicked)
```



---

## Useful Links

### Asynchronous JS

Introduction To Asynchronous Javascript - https://www.pluralsight.com/guides/introduction-to-asynchronous-javascript

6 Reasons Why JavaScript’s Async/Await Blows Promises Away (Tutorial) - https://hackernoon.com/6-reasons-why-javascripts-async-await-blows-promises-away-tutorial-c7ec10518dd9

Udemy - Asyncronous vs Syncronous - https://www.udemy.com/node-js-mongo-db-2018/learn/v4/t/lecture/10909474?start=0

How is javascript asynchronous AND single threaded? - https://www.sohamkamani.com/blog/2016/03/14/wrapping-your-head-around-async-programming/

Understanding Promises In Javascript - https://hackernoon.com/understanding-promises-in-javascript-13d99df067c1

--- 

![THANKS](https://media.giphy.com/media/KJ1f5iTl4Oo7u/giphy.gif)

---

## Question

- Does anyone know why the meaning of 'synchornous' and 'asynchronous' have been swapped in programming?
