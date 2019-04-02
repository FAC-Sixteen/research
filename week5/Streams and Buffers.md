# Streams and Buffers
![](https://media.giphy.com/media/PxSFAnuubLkSA/giphy.gif)

---

# Stream

![](https://media.giphy.com/media/5YuhLwDgrgtRVwI7OY/giphy.gif)

---

Streams are objects that **let you read data from a source or write data to the destination in a continuous fashion**.

You have a huge amount of data to process, but you don’t need to wait for all the data to be available before you start processing it.

This big data is broken down and **sent in chunks**. 

---

## Stream is Used In:
- HTTP request & responses
- Standard input/output(stdin & stdout)
- File reads and write
### Stream types:
- **Readable Stream** (input streams has data going into the applications)
- **Writable Stream** (output streams contain data going out of the applications)

---

# Buffer
![](https://media.giphy.com/media/UJR3QgkMnm7tu/giphy.gif)

---

- **Node.js will automatically create a buffer** when creating a stream
- Node.js can’t control the speed or time of data arrival, or the speed of the stream. It only **can decide when it’s time to send out the data.** **If it’s not yet time, Node.js will put them in the buffer** — the “waiting area” — a small location in the RAM, until it’s time to send them out for processing.

---

You can also create your own buffer like so:

```
//create an uninitiated Buffer of 10 octets
let bufferOne = new Buffer(10);
//create a Buffer from a given array
let bufferTwo = new Buffer([10, 20, 30, 40, 50]);
//create a Buffer from a given string
let bufferThree = new Buffer('Simply Easy Learning');
```

---

![](https://i.ytimg.com/vi/GlybFFMXXmQ/maxresdefault.jpg)

---

# Q: Who is the stream?

---

# A:
![](https://media.giphy.com/media/3o7btQrEwM9dOtjVmg/giphy.gif)

---

# Lets get Quizzical!

![](https://media.giphy.com/media/4WEUtXFFmRlRivIpEl/giphy.gif)

## [Test](https://forms.gle/L2RSjmBntRm9caya9)

---

## Resources:
Stream and Buffer Concepts in Node.js - https://medium.com/tensult/stream-and-buffer-concepts-in-node-js-87d565e151a0

Do you want a better understanding of Buffer in Node.js? Check this out - https://medium.freecodecamp.org/do-you-want-a-better-understanding-of-buffer-in-node-js-check-this-out-2e29de2968e8

Using Node.js to Read Really, Really Large Datasets & Files (Pt 1) - https://itnext.io/using-node-js-to-read-really-really-large-files-pt-1-d2057fe76b33

https://www.youtube.com/watch?v=GlybFFMXXmQ

https://forms.gle/L2RSjmBntRm9caya9
