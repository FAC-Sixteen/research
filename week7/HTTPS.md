# HTTP vs HTTPS

> Super useful link
> https://www.upwork.com/hiring/development/ssl-certificates/

## SSL and TLS 

 - Cryptographic protocols that provide authentication and data encryption
 - Secure methods of sending encrypted data between browser and server
 - Encrypted data can only be read by the person with encryption key

---

## Encrypted VS NOT Encrypted
![](https://i.ibb.co/ctDNGGd/What-Is-HTTPSEncryption.png)

----

### Why is this important to implement in your projects? - Ryan

---

* **Better SEO ranking.** 
    * SSL and HTTPS are not only valuable to security, but they’re also going to be helpful when it comes to SEO, ecommerce, and visual notifications about the security of a page in Google Chrome. The Google Security Team announced that the 56th version of Google Chrome will visually alert users when they’re not on a secure website with an SSL certificate.
    
---

* **Safer, more secure data transfer between servers, with less chance of interception**


* **Increased trust with customers**

* **SSL is required for Payment Card Industry (PCI) compliance.**

![reference link](https://media.giphy.com/media/l0ErBTfnwCom6mFPi/giphy.gif)

---

### How to generate certificates and use them in a node project 

---

There are a few ways to generate a certificate.
There are certification authorities who can issue you an official certificate, eg CloudFlare or Let's Encrypt.
- kind of long, requires a few different applications

---

Some hosting sites like Netlify will issue you a free certificate automatically.

---

You can also make your own certificate!

The easy way: https://flaviocopes.com/express-https-self-signed-certificate/

The long way: https://stackoverflow.com/questions/10175812/how-to-create-a-self-signed-certificate-with-openssl

---

![](https://media.giphy.com/media/PPi5c8l8WDY7if1L8z/giphy.gif)
