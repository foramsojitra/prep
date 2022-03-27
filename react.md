# Node.js

### Q : What is node.js? and How it works?
A : Node.js is a Server side scripting which is used to build scalable programs. Its multiple advantages over other server side languages, the prominent being non-blocking I/O.
Node.js works on a v8 environment, it is a virtual machine that utilizes JavaScript as its scripting language and achieves high output via non-blocking I/O and single threaded event loop.

### Q : What is the advantage of using node.js?
A : 
* It provides an easy way to build scalable network programs
* Generally fast
* Great concurrency
* Asynchronous everything
* Almost never blocks

### Q : What are the two types of API functions in Node.js ?
A : 
* Asynchronous, non-blocking functions
* Synchronous, blocking functions

### Q : What is control flow function?
A : A generic piece of code which runs in between several asynchronous function calls is known as control flow function.

### Q : What is an event loop in Node.js ?
A : To process and handle external events and to convert them into callback invocations an event loop is used. So, at I/O calls, node.js can switch from one request to another.An event loop in Node.js handles all the asynchronous callbacks in an application. It is one of the most important aspects of Node.js and the reason behind Node.js have non-blocking I/O. Since Node.js is an event-driven language, you can easily attach a listener to an event and then when the event occurs the callback will be executed by the specific listener. 

### Features of Event Loop:

* Event loop is an endless loop, which waits for tasks, executes them and then sleeps until it receives more tasks.
* The event loop executes tasks from the event queue only when the call stack is empty i.e. there is no ongoing task.
* The event loop allows us to use callbacks and promises.
* The event loop executes the tasks starting from the oldest first.
Example

https://www.youtube.com/watch?v=4lMN7EKdBdE&ab_channel=TechnologyAndProduct

### Q : What is event emitter in node js?
A : The EventEmitter is a module that facilitates communication/interaction between objects in Node. EventEmitter is at the core of Node asynchronous event-driven architecture.

### Q : What is an error-first callback in Node.js?
A : Error-first callbacks in Node.js are used to pass errors and data. The very first parameter you need to pass to these functions has to be an error object while the other parameters represent the associated data. Thus you can pass the error object for checking if anything is wrong and handle it. In case there is no issue, you can just go ahead and with the subsequent arguments.
```javascript
var myPost = new Post({title: 'edureka'});
myPost.save(function(err,myInstance){
if(err){
//handle error and return
}
//go ahead with `myInstance`
});
```

### Q :  Explain the concept of middleware in Node.js?
A : In general, middleware is a function receives the Request and Response objects. In other words, in an application’s request-response cycle these functions have access to various request &  response objects along with the next function of the cycle. The next function of middleware is represented with the help of a variable, usually named next.

### Q : For Node.js, why Google uses V8 engine?
A : Google uses V8 as it is a Chrome runtime engine that converts JavaScript code into native machine code. This, in turn, speeds up the application execution and response process and give you a fast running application.

### Q : What is the use of NODE_ENV?
A : If the project is in the production stage, Node.js promotes the convention of making use of NODE_ENV variable to flag it. This helps in taking better judgment during the development of the projects. Also, when you set your NODE_ENV to production, your application tends to perform 3 times faster.

### Q : Describe the exit codes of Node.js.
A : * Uncaught fatal exception
* Unused
* Fatal Error
* Internal Exception handler Run-time failure
* Internal JavaScript Evaluation Failure
* The exit code. Default: 0. process.exit(1); failure
