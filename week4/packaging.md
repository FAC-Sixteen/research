# PACKAGING

![packaging](https://thumbs.gfycat.com/RecentCraftyArizonaalligatorlizard-small.gif)

---

![a package](https://i.imgur.com/Zc9OsKi.png)

---

## Dependencies

---

+ **What is a dependency?**

![dependent](https://media.giphy.com/media/vIuMHJiulG9na/giphy.gif)

---

+ **Why might you want to use a dependency in your project, rather than writing the code from scratch?**

---

+ **What have traditionally been some of the issues with managing dependencies?**

---

+ What have traditionally been some of the issues with managing dependencies?

## PACKAGE TSUNAMI // DEPENDENCY HELL

---

! [package tsunami] (https://img.devrant.com/devrant/rant/r_1854993_fVsnT.jpg)

---

![dependency hell](https://i.imgur.com/IpottOP.gif)

---


![heaviest objects](https://i.octopus.com/blog/2018-05/deploying-nodejs/node_modules.jpg)


---

## NPM
package manager
All package managers do relatively the same thing. Move files.
Pick a package manager on how well it does that.

All build tools do relatively the same thing. Transform files.
Pick your build tools on how well they do that.

---

![](https://i.imgur.com/irZbxzq.png)

---

The crew it's self have support....

this where 
## DevDependencies 

come into play

---

unlike other package managers, npm installs a tree of dependencies. 

![gif of roomba shark](https://media.giphy.com/media/mokQK7oyiR8Sk/giphy.gif)

---

`npm init`

![](https://media.giphy.com/media/xTk9Zxw5LoEOuCLCQE/giphy.gif)

<initializer> can be used to set up a new or existing npm package.

---

A package.json file:

- lists the packages your project depends on
specifies versions of a package that your project can use using semantic versioning rules
- makes your build reproducible, and therefore easier to share with other developers

---

![package with devDependencies](https://i.imgur.com/dorH5Vk.png)

---

How do you use an installed package in your code?

require()
module.exports



module.js


---

## `npm install`

![npm install](https://i.octopus.com/blog/2018-05/deploying-nodejs/forrest.jpg)


---

### Three types of `npm install`

* **Dependency** - packages required to run the app
* **Dev Dependency** - packages required only during development
* **Globally** - packages you want to re-use across projects

* no matter how you install a package, it can always be accessed in your code with: 
`require('package-name')`


---

### Installing as a dependency 🤖

**How do I do this in the command line?** 🖥

* The long way:
`npm install --save-prod nodemon`
 
* The short way:
`npm i -P nodemon`

* The very short way:
`npm i nodemon`
* ↑ regular dependency is the default!


---

### Installing as a dependency 🤖

**When would I use this?**

* Use this as your default unless you know that the package you're installing is only going to be used by developers

* e.g. a nodemon server might need to be running for the app to work 


---

### Installing as a dev dependency 👾

**How do I do this in the command line?** 🖥

* The long way:
`npm install --save-dev tape`
 
* The short way:
`npm i -D tape`


---

### Installing as a dev dependency 👾

**When would I use this?**
* Use this when you know the package will only be needed for development
* e.g. testing is needed for us devs, but not for someone using our app.



---

### Installing globally 🌍

**How do I do this in the command line?** 🖥

* The long way:
`npm install --global nodemon`
 
* The short way:
`npm i -g nodemon`


---

### Installing globally 🌎

**When would I use this?**
 
* If you find that you re-use certain packages over and over in your projects, you may want to use this to install something globally
* e.g. you may want to use nodemon for testing/server in lots of your projects



---

### Installing globally 🌏

**Why this might be a bad idea...**

* You might want to have multiple different projects all working with different packages
* If you want to make a project that works when someone else clones it from GitHub, it needs to be self-contained
* If you update a global package, this may cause problems for projects in terms of backwards-compatability


---

# Package files
![](https://media.giphy.com/media/3o85xsGXVuYh8lM3EQ/giphy.gif)

---

# Where does NPM install packages? 

![sohot](https://media.giphy.com/media/l3q2xWsutZRLaiK5y/source.gif)

---

### 1. Global libraries.
### 2. Non-global libraries.

![sohot](https://media.giphy.com/media/vbD9OoDgUOpkk/giphy.gif)

---

#### Global libraries

Run 
```
npm list -g
```
**Unix:** 
```
/usr/local/lib/node
/usr/local/lib/node_modules
```

**Windows XP -** 
```
%USERPROFILE%\AppData\npm\node_modules
```
**Windows 7, 8 and 10 -** 
```
%USERPROFILE%\AppData\Roaming\npm\node_modules
```

---

# Non-global libraries
![sohot](https://media.giphy.com/media/bGGpcIS8PX1pm/giphy.gif)

---

#### Non-global libraries

Run
```
npm list
```
In the `node_modules` file.

Run `npm list`- shows installed non-global libraries for current location.

---

#### Why is it important to make sure that installed packages aren't included in your repositories?

Q: Why include or not?

![sohot](https://media.giphy.com/media/xqBpxjk7CXLtm/giphy.gif)

---

# Reasons for not including:
![sohot](https://media.giphy.com/media/KTW9FIyPKTFcI/giphy.gif)

---

#### Reasons for not including:

1. Keep your repo smaller.
e.g. node_modules is humongous.
2. Installed packages included in your repository will become out of date
i.e. a user may have to run npm install again anyway.
3. Users may wish to change packages or check before running project
e.g. if making project compatible with an existing project.

---

### Reasons for including:

![](https://media.giphy.com/media/khl6RE8XNiwxstKNzE/giphy.gif)

---

#### Reasons for including:

1. Removes the risk that 5 years down the line your code breaks., 
e.g. a particular dependency no longer works.
2. If Github has network issues, and you require the user to run `npm i` in order to use your project, your code will break.

---

#### How do you prevent Git from including these files in your repository?
![sohot](https://media.giphy.com/media/102AsbWPQZXbeU/giphy.gif)

---

1. Create a `.gitignore` file in your repository.
2. Add the line below onto its own line, in this file:

```/node_modules```

3. Now your node_modules file will ignored by git.

---

### Links


[https://addyosmani.com/blog/checking-in-front-end-dependencies/#more-5510](https://)

[https://blog.codeanalogies.com/2018/09/24/node-package-manager-npm-explained-by-directing-a-movie/](https://)

Meme-style pics from https://octopus.com/blog/deploying-nodejs

How to avoid Dependency hell https://medium.com/@andrerpena/a-trick-for-avoiding-dependency-hell-on-node-js-f6ff20a09578

[npm dependencies and devDependencies](https://flaviocopes.com/npm-dependencies-devdependencies/)

[npm global or local packages](https://flaviocopes.com/npm-packages-local-global/)
