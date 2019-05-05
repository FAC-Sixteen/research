# Deploying to 'The Cloud'

![deploy](https://i.imgur.com/KpHC4jL.gif)

---

### Cloud Platforms
- In the beginning there was the internet, a technology that accelerated society in a shorter time than any other.
- Then came the cloud, a type of internet-based computing that enables on-demand access to a shared pool of computing resourses.

---

### Why is a cloud platform useful? 
**Cost** - Cloud computing eliminates the capital expense of buying hardware and software.
**Speed** - Most cloud computing servives are provided as self service and on demand.
**Global Scale** - The ability to scale elastically. Delivering the correct amount of IT resources(more/less computing power,storage and bandwidth) where it's needed, from the correct geographical location.
**Productivity** - On-site data centres require a lot of hardware setup, software patching and other time-consuming IT management chores. Cloud computing removes the need for many of these tasks, so IT teams can spend more time achieving more important business goals.
**Performance** - The biggest cloud computing services run on a worldwide network of secure data centers, which are regularly updated to the latest generation of fast and efficient computing hardware.
**Security** - Many cloud providers offer a broad set of policies, technologies and controls that strengthen your overall security. Protrecting you from possible threats.


___

### What is PaaS?
- **Platform as a Service(PaaS)** is a category of cloud computing services that provides a platform allowing individuals to develop, run and manage applications.
- Because the underlying infrastructure is already written, tested, and optimized, the platform allows for low-code development that doesnt take a seasoned programmer to create something valuable


---

### What is Heroku?

- **Heroku** is a cloud platform that lets companies build, deliver, monitor and scale apps — they're the fastest way to go from idea to URL, bypassing all those infrastructure headaches.

---

### Alternates to Heroku

* AWS
* Oracle Cloud
* Nebula (NASA)
* Microsoft Cloud Services (Azure)

---

## Environment Variables
- a way of storing sensitive data such as:
-- API keys
-- Login credentials 
-- Database passwords
- env2 allows you to store your environment variables in an env.json or a .env which you would then add to your .gitignore file so that all your sensitive information wouldn't be public on GitHub

---



## Dangers of Careless Cloud Deployment

![](https://i.imgur.com/KgxPp1N.png)

- It's easy to make a costly mistake! 

---

### To get started with .env!
#### STEP 1: Create your .env file
Add all your secrets you dont want to share
![](https://i.imgur.com/x2DpEIx.png)


---

### env.json?

another way of writing your .env file (works just the same!)

![env.json](https://i.imgur.com/TdrycMR.png)

---
## STEP 2: Install env2 to your package.json

`npm install env2 --save`

---
## STEP 3: Require them in your project where you need them
![](https://i.imgur.com/uVbl64j.png)




---
## STEP 4: Add the .env file to .gitignore

![](https://i.imgur.com/9jtyPTG.png)

---
## STEP 5: Access them with `process.env`
![](https://i.imgur.com/vCSwqWi.png)

---

## What The Developer Sees

![](https://i.imgur.com/CVa3s2K.png)

## What Joe Public Sees

![](https://i.imgur.com/oWALimE.png)

---

## How To Share .env with your team

![](https://i.imgur.com/Og5gC39.png)

- Any way that you all agree is secure!

---


### Useful Resources
PaaS vs SaaS vs IaaS: https://www.bmc.com/blogs/saas-vs-paas-vs-iaas-whats-the-difference-and-how-to-choose/ 
