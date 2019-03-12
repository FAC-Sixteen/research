# CSS Philosophies



## **BEM (Block Element Modifier)**

### Summary

**BEM** (Block, Element, Modifier) is a front-end naming methodology for standardizing the structure of CSS through exclusive use of _class_ selectors.


A **block** is a stand-alone entity with semantic content (e.g. a header, container, or a menu).

```
.button
```

An **element** is the child of a block (e.g. a menu item, list item, or a checkbox caption). It inherits its semantic content from its parent.

```
.button__state
```

A **modifier** is a flag on a block or element (e.g. a change in colour, or margin, or border-radius).

```
.button__state--danger
```

In BEM there is no stand-alone content. Every item in a document is styled by reference to a block, element or modifier. 

In other words, you don't use IDs anymore. Forget `<button id = button1>`!

![no ID needed](https://i.imgur.com/haA9xKW.gif)





---

### Pros and Cons

*Pros:*

- **Avoid block style dependencies**: CSS inheritance is otherwise infinite!
- **Readability**: standardized code gives greater transparency and legibility to other coders' CSS.
- **Modularity**: breaks big projects into digestible chunks. 
- **Intuitive structure** and grouping, e.g:
     
        <button class="button"> Normal Button </button> 
        <button class="button__state--danger--big-big"> Big Danger Button </button>
        <button class="button__state--safe"> Safe Button </button>
        <block__modifier--value>
        
*Cons:*

- *Cannot* use **general references** to variables used throughout the document (e.g. a theme colour).
- Blocks *cannot* be **cross dependent** (e.g. a block like `.button` cannot use the code of another block's element, such as `.switch__state`).
- As a result of the above, code is **repeated** throughout the document, creating obsoletion. 
        
        


---

## **Design Techniques**

### Responsive Design

![Difference between responsive and adaptive](https://i.imgur.com/fst8YVd.gif)
</br>


Responsive websites scale dynamically when you resize your browser.

### How Not To Do It:

![](https://i.imgur.com/NcXnbxQ.gif)


*Pros:*

+ Cost Effective.
+ Great for sites which require lots of content.
+ Improve SEO stats. 


*Cons:*
* The mobile experience is not 100% optimized.

---
# Adaptive Design


Adaptively designed websites change to fit **specific widths** on desktop, tablet and mobile screens.

The most common viewport widths are: 
**320px, 480px, 760px, 960px, 1200px, and 1600px**

![](https://i.imgur.com/OU4kvyD.png)

### How To Do It:

![](https://i.imgur.com/ufVCgNv.gif)

</br>

*Pros:*
+ Good for satisfying different user intents
+ Retrofitting existing websites
+ Good for testing different layouts

*Cons:*
* Resource and budget heavy.
* Complexity.

---

# Mobile-first

'Mobile-first' is a strategy where you design for the smallest device first, then scale up.

*Pros:*
* Better Experience on mobiles.
* Majority of internet browsing on a smartphone with expected users of 75% in the future.
* Cheaper than building an iOS, Android or Hybrid App.


*Cons:*
* The desktop experience is not 100% optimized.
* Not ideal for website which have a lot of content.

---
### Resources
**BEM**
- http://getbem.com/introduction/
- https://csswizardry.com/2013/01/mindbemding-getting-your-head-round-bem-syntax/
- https://www.smashingmagazine.com/2018/06/bem-for-beginners/
- https://blog.decaf.de/2015/06/24/why-bem-in-a-nutshell/
- https://www.youtube.com/watch?v=SLjHSVwXYq4&t=253s
