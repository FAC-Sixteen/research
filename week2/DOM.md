### DOM (e-matrix)

The *Document Object Model* is a tree of nodes (HTML elements):

![DOM tree](https://i.imgur.com/lj8HGND.gif)

We use it as an interface between Javascript and HTML. It makes our HTML and CSS **dynamic**.

____

***1. How can you use JavaScript to create an HTML element and then add it to your webpage? How would you replace an existing element with it?***


**Use the createElement() method for creating a DOM element:**

```JavaScript
var el = document.createElement('div');
```

```JavaScript
var textnode = document.createTextNode('Hello World!');

el.appendChild(textnode); 
```
"el" can now be inserted into the DOM tree:
```JavaScript
document.body.appendChild(el);
```

___

**Replacing one element with replaceChild():**

``` JavaScript
// select the element that will be replaced
var el = document.querySelector('div');

var newEl = document.createElement('p');
newEl.innerHTML = '<b>Hello World!</b>';

// replace el with newEL
el.parentNode.replaceChild(newEl, el);
```

---


***2. How would you add a `<li>` element to the start of a `<ul>`?***

```HTML
<html>
<body>

<ul id="myList">
  <li>Coffee</li>
  <li>Tea</li>
</ul>


<button onclick="myFunction()">Try it</button>


<script>
function myFunction() {
  var newItem = document.createElement("LI");
  var textnode = document.createTextNode("Water");
  newItem.appendChild(textnode);

  var list = document.getElementById("myList");
  list.insertBefore(newItem, list.childNodes[0]);
}
</script>

</body>
</html>
```

1. First create a LI node,
2. Then create a Text node,
3. Then append the Text node to the LI node.
4. Finally insert the LI node before the first child node in the list.

---

3. ***What is a JavaScript Event? What does event.preventDefault() do and why might you use it?***

"An Event allows for signaling that something has occurred"(DOM4 spec)
- events are triggered by user actions, programmatically (calling the HTMLElement.click() method of an element).
- creates an Event Object

...basically, events are "things" that happen to html elements

Common events that happen to elements include:
* **onchange**, an HTML element has been changed
* **onclick**, the user clicks an HTML element
* **onkeydown**, the user pushes a keyboard key
* **onload**, the browser has finished loading the page

When can we use it?
- each event has a "canceled flag" initially unset.
- if event.cancelable (read-only prop) returns true this indicates that part of the operation during which the event was dispatched, can be canceled by invoking the preventDefault() method.

What does it do?
- cancels the event if it is cancelable, meaning that the default action that belongs to the event will not occur (the related script is not executed)

Why would we use it?
- we use preventDefault() tells JS to not handle the default action for which a DOM element has been setup to "listen" for or accept (Event handlers). Used to limit the scope of possible actions for the user. e.g making an input area in a form not accept (cannot enter) capitalized characters. 
- e.g a list of criterias and respective checkboxes. If some criteria are incompatible, then a preventDefault() might be appended to the event to prevent selection of conflicting criteria. Single? Married? selection of the former, triggers script disallowing entry in the "spouse's name:" input.



* Definition: https://www.w3schools.com/js/js_events.asp
* preventDefault: https://www.w3schools.com/jsref/event_preventdefault.asp

---

4. ***What is a NodeList? How is it different from an Array?***

![A ray.](https://i.imgur.com/PtZaNMf.gif)

 
NodeLists are a language-independent way to access DOM elements.

Arrays are JavaScript objects.

They are both lists / arrays of elements.

---

We make NodeLists by using DOM methods such as .querySelectorAll or .childNodes:
```
var NodeList1 = document.querySelectorAll("p");
var NodeList2 = document.ul.childNodes;
```

---

Items in a nodeList are accessed by index in either of two ways:
* `list.item(0)`
* `list[0]`

A NodeList can be converted to a real array using Array.from():

```
var listArray = Array.from(NodeList2);
```
 
 ---
 
 
 In some cases, the NodeList is live, which means that changes in the DOM automatically update the collection.
 
 e.g. `Node.childNodes`
 
 In other cases the NodeList is static, and changes in the DOM do not affect the content of the collection. 
 
 e.g.`document.querySelectorAll()`
 
 


---

## Element.innerHTML 

![hacking](https://media.giphy.com/media/UqxVRm1IaaIGk/giphy.gif)

 
 
---
 
 HTML5 specifies that a ```<script>``` tag inserted with innerHTML should not execute.

Internet Explorer when the HTML string contains a script tag marked as deffered: ```<script defer>...<script>```  

IE8 - toStaticHTML function 


---
### However
```<img src="!@#$" onerror="function do_something(){scary thing and ever scarier things}" />```

---
other issues - destroys existing HTML elements

if event handlers attached to them, potentially creating a memory leak on some browsers.

---
### Better Practice 
 use `.textContent` for text-only tags 
 
 `.appendChild` for nodes (usually created with `.createElement`)



``` JavaScript
var x = document.createElement("IMG");
x.src = "hackanm.gif";
```


---

Other links:

https://www.w3.org/TR/domcore/#concept-event - jump to events
https://javascript.info/bubbling-and-capturing - bubbling and capturing
