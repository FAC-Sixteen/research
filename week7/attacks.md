# Attacks

---

# Malcolm In The Middle (MITM)

![](https://media.giphy.com/media/KwU7HpvgpMrOE/giphy.gif)

---

## attac 

A man in the middle attack is where a third party eavesdrops on the communication between two parties. This can occur physically in the real world, which we don't care about, or it can happen utilising malicious software. 

---

The most important part though is that the 'man' is not detected. Phishing emails are a type of MITM attack.

---

A man in the middle attack has two stages:

 1. interception
 2. decryption

---

The most common form of interception is where attackers access unsecure wifi connections, such as a public wifi service, or even home wifi that has a s**t password.

Once they have gained access, they can install tools to a users computer on that network to gather the data they want, such as bank details.

---

Once they have that data they then have to *decrypt* it so that they can then preceed to steal all your money.

There are many others ways that a bad guy can get the malware on your computer, or on a website.

---

## protec

Protecting against man in the middle attacks is quite simple.

For ones involving you home computer all you need to do is ensure that you have a good security software to detect malware, this should pickup attempts. But you also want to have a good secure password on your wifi itself. Your security on your computer won't do s**t if someone gets access to your router.

---

You also want to avoid connecting to public wifi without a vpn to protect your information.

One of the easiest ways though when browsing the internet is to make sure that sites you access are https rather than http.

---

# Cross Site Scripting (XSS)

![](https://media.giphy.com/media/3o6MbaH4zqUQ3wydlC/giphy.gif)

---

## attac 

Cross-site scripting originally meant attacking a web page from an unrelated attack-site (hence *cross* site scripting), but now refers to a broad range of code injections. 

---

Injections involve inserting client-side scripts into web pages viewed by other users. The attackers' code becomes combined with the code of the compromised site, and so it appears to be delivered from the trusted source.

---

There are two primary flavors of XSS: non-persistent and persistent.

---

1. Non-persistent (or *reflected*) attacks: 

The attacker finds an input field that has not been sanitised, for example a comment field, and inserts a malicious link into the input.

---

The user is lured into clicking on the link, which initiates the XSS request to an exploited website, reflecting the attack back to the user.

---

![](https://media.giphy.com/media/zNXvBiNNcrjDW/giphy.gif)

---

2. Persistent (or *stored*) attacks:

The data provided by the attacker is saved by the server, and then permanently displayed on 'normal' pages returned to other users in the course of regular browsing.

---

This means the attacker's malicious script is rendered automatically, without the need to individually target victims or lure them to a third-party website.


---

## protec

* Contextual output encoding/escaping of string input
* Safely validating untrusted HTML input
* Cookie security
* Disabling scripts
* Emerging defensive technologies


---

## Cross Site Request Forgery (CSRF)

![](https://media.giphy.com/media/xT5LMM07p6oX0EzDC8/giphy.gif)

---

## attac

* Cross site requests do not need your permission so an attacker can abuse this and send requests without your consent and without you noticing
* if the user is currently authenticated to the site, the site will have no way to distinguish between the forged request sent by the victim and a legitimate request sent by the victim.
![](https://media.giphy.com/media/134DVXcD94sOWI/giphy.gif)

---

![csrf](https://www.imperva.com/learn/wp-content/uploads/sites/13/2019/01/csrf-cross-site-request-forgery.png)

`<a href="http://netbank.com/transfer.do?acct=AttackerA&amount=$100">Read more!</a>`

---

## protec

### an Anti-CSRF Token 
An Anti-CRSF token is a random string that is only known by the user’s browser and the web application. It is usually stored inside a session variable. It is typically on a page inside a hidden form field which is sent together with the request. 


---

## more protec

### Use the Same-Site Flag in Cookies 
If the session cookie is marked as Same-Site cookie, it is only sent along with requests that originate from the same domain.

---

![](https://i.imgur.com/wnMRDkJ.png)

---

![](https://www.meme-arsenal.com/memes/34249a4f60e9439ab04c12f2ffc7c6d4.jpg)

---

## References

![reference link]()

[MITM](https://us.norton.com/internetsecurity-wifi-what-is-a-man-in-the-middle-attack.html)
[CSRF](https://www.imperva.com/learn/application-security/csrf-cross-site-request-forgery/)

![](https://i.imgur.com/DSpq0gn.jpg)


