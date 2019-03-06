# Accessibility 🚦

---

## Accessible Navigation 🏔

---

### Access keys 🗝
* In the olden days...
* A single key will select a menu item
* The W3C introduced the `accesskey` attribute to enable users to select the appropriate key on their keyboards and navigate to a particular link. 
* for example `accesskey="s"` used to navigate to menu items using the keyboard "s" 

---

### ARIA 💃
* Accessible Rich Internet Applications (ARIA)
* Set of attributes that add context to a webpage for those with disabilities
* e.g. `<button aria-label="this button clicks things">Click</button>` will tell someone with a screen reader what the button does

---

``` html
<div role="navigation" aria-label="Main navigation">
  <!-- list of links to main website locations -->
</div>
```
* Tells a screen reader that the purpose of the div is navigation, and that it is the main navigation menu

---

### `<nav>` Elements 🧭 🌍🌬🔥🌊
* Semantic HTML - use `<nav>` element to identify a section of the page which will be used for navigation links
* Replaces the ARIA `role` and adds more structure and meaning to divs
* This is only really intended for blocks of main navigation links

---

### Some Common Sense Stuff Not to Do ❌
* Setting something to `display: none` in CSS
* Navigation menus that can only be accessed by hovering - [example](https://www.w3schools.com/howto/tryit.asp?filename=tryhow_css_dropdown_navbar)
* Instead use `:focus` and `focus-within` - uses tab key to navigate through each drop-down item  - [example](https://codepen.io/AtomicSmash/pen/PaLNMe?editors=1100)


---

## Accessible Modal 🔓

![](https://i.imgur.com/2GYfJrd.png)

**Modal dialog** (interactive window) must be accessible for the users who are navigating a site via a keyboard and/or screenreader

---

## How to create an accessible modal? 🤔

---

### Use appropriate markup and ARIA attributes to provide descriptive text for screenreaders

---

### ARIA attributes: 
- **aria-labelledby** attribute establishes relationships between objects and their label(s), and its value should be one or more element IDs, which refer to elements that have the text needed for labeling.

``` html
<div id="myBillingId">Billing</div>

<div>
    <div id="myNameId">Name</div>
    <input type="text" aria-labelledby="myBillingId myNameId"/>
</div>
<div>
    <div id="myAddressId">Address</div>
    <input type="text" aria-labelledby="myBillingId myAddressId"/>
</div>
```

---


- **aria-label** attribute is used to define a string that labels the current element. Use it in cases where a text label is not visible on the screen. If there is visible text labeling the element, use **aria-labelledby** instead.

``` html
<button aria-label="Close" onclick="myDialog.close()">X</button>
```

---


- **aria-describedby** attribute is used to indicate the IDs of the elements that describe the object. It is used to establish a relationship between widgets or groups and text that described them. It is similar to **aria-labelledby** but provides more information that the user might need.
``` html
<button aria-label="Close" aria-describedby="descriptionClose" 
    onclick="myDialog.close()">X</button>

...

<div id="descriptionClose">Closing this window will discard any information entered and 
return you back to the main page</div>
```

---

``` html
<div class="dialog" role="dialog" aria-labelledby="dialog-title" aria-describedby="dialog-description">
	<h1 id="dialog-title">Site Navigation</h1>
	<p id="dialog-description" class="sr-only">Description goes here</p>
	<nav>
		<ul>
			<li><a href="one.html">Link One</a></li>
			<li><a href="two.html">Link Two</a></li>
			<li><a href="three.html">Link Three</a></li>
		</ul>
	</nav>
	<button type="button" aria-label="Close Navigation" class="close-dialog"> <i class="fa fa-times"></i> </button>
</div>
```

---

### On dialog opening, set focus 🔬

*When opened, focus should be on the first  focusable element within the dialog*

- Generate an array of all focusable elements within the dialog
- Elements that receieve focus are anchors, form input elements, buttons, and any element with a 'tabindex' of '0' or greater
- We can get the array by querying the document for any of these elements

---

```html
function Dialog(dialogEl, overlayEl) {
    
    this.dialogEl = dialogEl;
    
    var focusableEls = this.dialogEl.querySelectorAll('a[href], area[href], input:not([disabled]), select:not([disabled]), textarea:not([disabled]), button:not([disabled]), [tabindex="0"]');
  
}
```

---

- We can get the first of these focusable elements and use the focus() method to direct focus to it

---

```html
this.firstFocusableEl = focusableEls[0];
this.firstFocusableEl.focus();
```

---

- There should be at least one focusable element in the dialog
- If there are no focusable elements, there should still be a button that closes the dialog itself

---

### On dialog close, return focus to the last focused element 👓

- you can determine which element opened the dialog by checking the active element in the document
- after the dialog is closed you can set this element back to focus 


``` html
Dialog.prototype.close = function() {
    this.focusedElBeforeOpen.focus();
};
```

---


### ⛔️Prevent mouse clicks outside the dialog while open

*Users should not be able to click on elements outside the dialog window*

- This can be achived by styling of the dialog overlay element

1) Position the overlay on the z-axis between the dialog itself and the rest of the body content

```html
.dialog { z-index: 3; }
.dialog-overlay { z-index: 2; }
.body-content { z-index: 1; }
```
2) Make sure that the overlay takes up the entire viewport

```htmlmixed=
.dialog-overlay {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0,0,0,0.7);
}
```
3) In our HTML, we set a 'tabindex' of '-1' on the overlay to prevent it from recieving focus

```htmlmixed=
<body>
	<div class=“body-content”></div>
	<div class=“dialog”></div>
	<div class=“dialog-overlay” tabindex="-1"></div>
<body>
```

---

### ⛔️Prevent tabbing outside the dialogue

- make sure that the user can tab forward (TAB) from the last back to the first element and backward (SHIFT + TAB) from first to last

- if there is only one focusable element, prevent any behaviour from happening when the user presses TAB

---

``` html
Dialog.prototype.handleKeyDown = function(e) {

	var Dialog = this;
	var KEY_TAB = 9;

	function handleBackwardTab() {
		if ( document.activeElement === Dialog.firstFocusableEl ) {
			e.preventDefault();
			Dialog.lastFocusableEl.focus();
		}
	}
	function handleForwardTab() {
		if ( document.activeElement === Dialog.lastFocusableEl ) {
			e.preventDefault();
			Dialog.firstFocusableEl.focus();
		}
	}
};
```

---

### Allow the _ESC_ key to close the dialog 🚪

*When the dialog is open, pressing the **ESC** key should close it*

- Besides the **TAB** key, all keys should work as normal
- Which means, **ESC** should close anything that is open


---

Thank you! 🐙

___
