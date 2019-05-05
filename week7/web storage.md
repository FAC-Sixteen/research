# RESEARCH: WEB STORAGE

**With web storage, web applications can store data locally within the user's browser.**

Before HTML5, application data had to be stored in cookies, included in every server request. Web storage is more secure, and large amounts of data can be stored locally, without affecting website performance.

Unlike cookies, the storage limit is far larger (at least 5MB) and information is never transferred to the server.

Web storage is per origin (per domain and protocol). All pages, from one origin, can store and access the same data."

## What are local storage and session storage and what is the difference between the two?
Web Storage API: provides 2 mechanisms by which browsers can store key/value pairs. 
- **Local Storage**: no expiration time on data (Window.localStorage)
- **Session Storage**: data is cleared once the session ends (when you close the browser) (Window.sessionStorage)

### Local storage
- local storage can only be cleared through javascript, or by clearing your browser cache
- https://dev.to/rdegges/please-stop-using-local-storage-1i04
![stop](https://i.imgur.com/2kYTuzM.png)
- In practice, local storage is just one big old JavaScript object that you can attach data to (or remove data from).

PROS
+ They don't need any backend language or logic to store data in the browser

### Session storage
- opening a new tab or window in your browser will open a new session

### Cookies
- What are cookies?
Cookies are small items of data, each consisting of a name and a value, stored on behalf of a website by visitors’ web browsers.

https://scotch.io/@PratyushB/local-storage-vs-session-storage-vs-cookie

## Why would you use cookies vs local/session storage?

**What is storage persistence?**
- It is essentially how long your data stays around for after the process that created your data has ended.

**How much data can you store in a cookie?**
- 4kb.

**How much data can you store in local/session storage?**
- 5mb.

**Why would you use cookies over local/session storage?**
1. sessionStorage is only available for the duration of the browser session (and is deleted when the tab or window is closed) - it does however survive page reloads.
2. The data stored in localStorage persists until explicitly deleted. Changes made are saved and available for all current and future visits to the site.

**Why would you use local/session storage over cookies?**
1. A big technical difference is the size of data you can store, and as I mentioned earlier localStorage gives you more storage space.
2. Cookies only allow you to store strings.
3. sessionStorage and localStorage allow you to store JavaScript **primitives** but not Objects or Arrays.

**Why would you use local storage over session storage?**
1. localStorage and sessionStorage are relatively new APIs and are near identical (both in APIs and capabilities) with the sole exception of persistence. 

## Demo a simple usage of localStorage and sessionStorage

https://repl.it/@samdickeson/web-storage-demo

**Storage Methods**
- Storage.setItem -> creates or updates the Storage object
- Storage.getItem -> gets the value of the (given) key from the Storage object

![](https://i.imgur.com/WyHo6OG.png)
