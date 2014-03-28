Web Worker
===

purpose
---

javascript is a single thread language, it uses web worker to accomplish multi-thread programming.
each work is defined by a javascipt file
self.onmessage and self.postMessage are used to communicate between worker and its creator


####**web worker can**

 - import other javascipt file
 - create nested worker
 - send/receive message from/to its creator

####**types**

 - **dedicated worker** `window.Worker`
    - linked to its creator, each time a dedicated worker is created, a new thread and instance is created


 - **shared worker** `window.SharedWorker`

   - can be shared between multiple windows from the same origin/domain
   - shared workers with the same name correspond to the same instance


dedicated worker
---

####**Creater Side**
```javascript
var newThread = new Worker('worker.js');

newThread.onmessage = function(e){
    // handle message from worker
    console.log(e.data); // e.data is the message
}

newThread.postMessage(); // send message to worker

newTread.terminate(); // stop a specific worker
```

####**Worker Side**
```javascript
importScripts('script1.js', 'script2.js'); // import additional scripts inside worker

newThread.onmessage = function(e){
    // handle message from creator
    console.log(e.data); // e.data is the message
}

newThread.postMessage('message'); // send message to creator

newThread.close(); // stop itself
```

shared worker
---

####**Creator Side**

```javascript
var shared = new SharedWorker('sharedworker.js');

shared.port.onmessage = function(e) {
    // need a port to connect to the shared worker
    console.log(e.data);
}
```


####**Worker Side**

```javascript
self.onconnect = function(e) {
    e.ports[0].onmessage = function(e, port) {
        console.log(e.data);
        port.postMessage('message'); // port is the connection to the sender
    }
}
```


---

references

[Introduction to HTML5 Web Workers: The JavaScript Multi-threading Approach](http://msdn.microsoft.com/en-us/hh549259.aspx)

[An Introduction to HTML 5 Web Workers](http://cggallant.blogspot.com/2010/08/introduction-to-html-5-web-workers.html)

[A Deeper Look at HTML 5 Web Workers](http://cggallant.blogspot.com/2010/08/deeper-look-at-html-5-web-workers.html)

[Using Web Workers to improve performance of image manipulation](http://blogs.msdn.com/b/eternalcoding/archive/2012/09/20/using-web-workers-to-improve-performance-of-image-manipulation.aspx)