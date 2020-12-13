# Javascript(#javascript)


# Javascript

### Q : What is js?
A : JavaScript is a programming language commonly used in web development. It was originally developed by Netscape as a means to add dynamic and interactive elements to websites.JavaScript is a synchronous, blocking, single-threaded language.
JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during run-time in contrast to statically typed language, where the type of a variable is checked during compile-time.

### Q : Difference between "var", "let" and "const"
A : var is there from the begining of the js, let and const introduced in ES6 all of this can be used for variable declaration. 
var declarations are globally scoped or function/locally scoped. 
var variables can be re-declared and updated : 
 ```javascript
      var a = 1;
      var a = 2; 
        OR
      var a = 1;
      a = 2;
--------------------
  function newFunction() {
  if(true){
          var a = "hello";
      }
  console.log(a);
  }
result will be => hello
--------------------
console.log(a);
      var a = 1;
 this code will interpreted as 
    var a;
    console.log(a); // a is undefined
    a = 1;
```

let has a block scope
```javascript
  function newFunction() {
  if(true){
          let a = "hello";
      }
  console.log(a);
  }
result will be => VM250:5 Uncaught ReferenceError: a is not defined
```
* var declarations are globally scoped or function scoped while let and const are block scoped.
* var variables can be updated and re-declared within its scope; let variables can be updated but not re-declared; const variables can neither be updated nor re-declared.
* They are all hoisted to the top of their scope. But while var variables are initialized with undefined, let and const variables are not initialized.
* While var and let can be declared without being initialized, const must be initialized during declaration.

### Q : What is event bubbling and capturing?
A : Event bubbling and capturing are two ways of event propagation

When an event happens on an element, it first runs the handlers on it, then on its parent, then all the way up on other ancestors.
If you have event on body and some parent and child element than when you click on child element it will execute event on the child firstevent bubbling execute the lowest order first so child element's event will execute first than it will check if parent element has any event if it has than it will be executed and after that if body element has any event that will be executed.

* Events first are captured down to deepest target, then bubble up. In IE<9 they only bubble.
* All handlers work on bubbling stage excepts addEventListener with last argument true, which is the only way to catch the event on capturing stage.
* Bubbling/capturing can be stopped by event.cancelBubble=true (IE) or event.stopPropagation() for other browsers.

### Q : What are the different data types present in javascript?
A : There are two types of data types in JavaScript.
~~~
 1. Primitive data type
 2. Non-primitive (reference) data type

 JavaScript primitive data types : 
    String, Number, Boolean, Undefined, Null

 JavaScript primitive data types : 
    Object, Array, RegExp
~~~
The difference between primitives and non-primitives is that primitives are immutable and non-primitives are mutable.

### Q : What is mutable and immutable data types in javascript?
A : Image result for what is mutable and immutable data types in javascript Mutable objects are objects whose value can change once created, while immutable objects are those whose value cannot change once created. 

Primitives are known as being immutable data types because there is no way to change a primitive value once it gets created.
~~~
var myString = "Helllooo"

console.log('myString[2]', myString[2]);

myString[2] = 'c'

console.log(myString);

==> result : myString[2] l
             Helllooo

As u can see value of string does not changed to Hecllooo cause string is immutable
~~~
On the other hand Non-primitives are known as being mutable data types like Arrays and Objects.
~~~
var x = {
    foo: 'bar'
};
var  y = x;
x.foo = 'Something else';
console.log(y.foo); // Something else
console.log(x === y) // true

As you can see, x is a mutable object, and any change in the property of x gets reflected in the value of y.
They all share the same reference. So, when you update the value of a property of x, you’re modifying 
the value for all the references to that object.
~~~

### Q : Difference between "==" and "===" 
A : == compares value and === compares vlue and type
== convert type of right side to type of left and then compare

### Q : Difference between null and undefined
A : both of them is an empty value but difference is that when you define a variable and not assign any value it automatically so you don't have to assign value undefine js do it for you. In case of null you have to assugn value null to variable. Typeof undefined will be undefined while typeof null will be object.

### Q : What is use of arrow 
A : arrow functions were introduced in ES6.
* Unlike regular functions, arrow functions do not have their own this. The value of this inside an arrow function remains the same throughout the lifecycle of the function and is always bound to the value of this in the closest non-arrow parent function.
* The handling of this is also different in arrow functions compared to regular functions.
* In short, with arrow functions there are no binding of this.
* In regular functions the this keyword represented the object that called the function, which could be the window, the document, a button or whatever.
* With arrow functions the this keyword always represents the object that defined the arrow function.
```javascript
let add = (x, y) => x + y;
--------------------------
let me = { 
 value: 1, 
 thisInArrow:() => { 
 console.log(this.value); // no 'this' binding here 
 }, 
 thisInRegular(){ 
 console.log(this.value); // 'this' binding works here 
 } 
};
me.thisInArrow(); 
me.thisInRegular();
==> result : undefined
             1
```
### Q : What would be the result of 3+2+"7"?
A : Since 3 and 2 are integers, they will be added numerically. And since 7 is a string, its concatenation will be done. So the result would be 57.

### Q : What is type of null and function?
A : type of null is "object" and type of function is "function".

### Q : What is closure and counter dillema?
A : We can create nested functions in JavaScript. Inner function can access variables and parameters of an outer function (however, cannot access arguments object of outer function).
A JavaScript closure is when an inner function has access to its outer enclosing function's variables and properties. like bwlow example.

```javascript
function OuterFunction() {

    var outerVariable = 1;

    function InnerFunction() {
        alert(outerVariable);
    }

    InnerFunction();
}
```
### Q : What is currying in JavaScript?
A : Currying is an advanced technique to transform a function of arguments n, to n functions of one or less arguments.
```javascript
function add (a) {
  return function(b){
    return a + b;
  }
}

add(3)(4) ==> 7
```
### Q : What are object prototypes?
A : All javascript objects inherit properties from a prototype.

For example,
Date objects inherit properties from the Date prototype
Math objects inherit properties from the Math prototype
Array objects inherit properties from the Array prototype.
On top of the chain is Object.prototype. Every prototype inherits properties and methods from the Object.prototype.
A prototype is a blueprint of an object. Prototype allows us to use properties and methods on an object even if the properties and methods do not exist on the current object.

### Q : What is prototypal inheritance?
A : When we read a property from object , and it's missing, JavaScript automatically takes it from the prototype. In programming, such thing is called “prototypal inheritance”.
```javascript
let car = function(model) {
 this.model = model;
};

car.prototype.getModel = function() {
 return this.model;
}

let a = new car('Toyota');
console.log(a.getModel());
}
==> result: Toyota
```
### Q : Function Declarations vs. Function Expressions
A : 
```javascript
//Function Declarations
function a() {
 console.log('Hello');
}

//Function Expressons
var a = function() {
 console.log('Hello');
}
```
### Q : What do you understand by Callback and Callback hell in JavaScript?
A : Callback: callback is a function that will be executed after another function gets executed.
. It is used to handle the execution of function after the completion of the execution of another function. A callback would be helpful in working with events. In the callback, a function can be passed as an argument to another function. It is a great way when we are dealing with basic cases such as minimal asynchronous operations.
```javascript
function divideByHalf(sum){
  console.log(Math.floor(sum / 2));
}
function multiplyBy2(sum){
  console.log(sum * 2);
}
function operationOnSum(num1,num2,operation){
  var sum = num1 + num2;
  operation(sum);
}
operationOnSum(3, 3, divideByHalf); // Outputs 3
operationOnSum(5, 5, multiplyBy2); // Outputs 20
```
Callback hell: When we develop a web application that includes a lot of code, then working with callback is messy. This excessive Callback nesting is often referred to as Callback hell.

### Q : What is promises?
A : Promises are used to handle asynchronous operations in JavaScript. 
it has 4 state: 
* fulfilled: Action related to the promise succeeded
* rejected: Action related to the promise failed
* pending: Promise is still pending i.e not fulfilled or rejected yet
* settled: Promise has fulfilled or rejected
```
var promise = new Promise(function(resolve, reject) { 
  const x = "geeksforgeeks"; 
  const y = "geeksforgeeks"
  if(x === y) { 
    resolve(); 
  } else { 
    reject(); 
  } 
}); 
  
promise. 
    then(function () { 
        console.log('Success, You are a GEEK'); 
    }). 
    catch(function () { 
        console.log('Some error has occured'); 
    }); 
```
### Q : What is an Immediately Invoked Function in JavaScript?
A : An Immediately Invoked Function ( known as IIFE and pronounced as IIFY) is a function that runs as soon as it is defined.
```javascript
(function(){ 
  // Do something;
})();
```

### Q :  Explain Implicit Type Coercion in javascript.
A : Implicit type coercion in javascript is automatic conversion of value from one data type to another. It takes place when the operands of an expression are of different data types.
* String coercion
String coercion takes place while using the ‘ + ‘ operator. When a number is added to a string, the number type is always converted to the string type.
```javascript
var x = 3;
var y = "3";
x + y // Returns "33" 
```
### Q : Explain Hoisting in javascript.
A : Hoisting is a default behaviour of javascript where all the variable and function declarations are moved on top. This means that irrespective of where the variables and functions are declared, they are moved on top of the scope. The scope can be both local and global.
```javascript
hoistedVariable = 3;
console.log(hoistedVariable); // outputs 3 even when the variable is declared after it is initialized	
var hoistedVariable;
```
To avoid hoisting, you can run javascript in strict mode by using “use strict” on top of the code.

### Q : console.log(6<7<8) ?
A : true
it counts from left to right and  6<7 is true and true means 1 so after 1st comparision it become 1<7 which is true so answer will be true.

### Q : What is ECMA Script and How are JavaScript and ECMA Script related?
ECMA Script are like rules and guideline while Javascript is a scripting language used for web development.

### Q : What are some of the features of ES6?
A : 
*Support for constants (also known as “immutable variables”)
*Block-Scope support for both variables, constants, functions
*Arrow functions
*Extended Parameter Handling
*Template Literals and Extended Literals
*Spread operator
*Destructuring Assignment

### Q : What is memoization?
A : Memoization is an optimization technique that speeds up applications by storing the results of expensive function calls and returning the cached result when the same inputs are supplied again.
Memoization is used for expensive function calls but in the following example, we are considering a simple function for understanding the concept of memoization better.
```javascript
function memoizedAddTo256(){
  var cache = {};

  return function(num){
    if(num in cache){
      console.log("cached value");
      return cache[num]

    }
    else{
      cache[num] = num + 256;
      return cache[num];
    }
  }
}

var memoizedFunc = memoizedAddTo256();

memoizedFunc(20); // Normal return
memoizedFunc(20); // Cached return
```
Although using memoization saves time, it results in larger consumption of memory since we are storing all the computed results.

### Q : What is a Temporal Dead Zone?
A : Temporal Dead Zone is a behaviour that occurs with variables declared using let and const keywords.
It is a behaviour where we try to access a variable before it is initialized.
```javascript
x = 23; // Gives reference error

let x;


function anotherRandomFunc(){
  message = "Hello"; // Throws a reference error

  let message;
}
anotherRandomFunc();
```
### Q : What is Higher-Order Functions?
A : In Javascript, functions are values ( first-class citizens ). This means that they can be assigned to a variable and/or passed as a value. 
A function that accepts and/or returns another function is called a higher-order function. The map function is one of the many higher-order functions built into the language. sort, reduce, filter, forEach are other examples of higher-order functions built into the language.
For example, the map function on arrays is a higher order function. The map function takes a function as an argument.
```javascript
const double = n => n * 2
[1, 2, 3, 4].map(double) // [ 2, 4, 6, 8 ]
--- OR ---
[1, 2, 3, 4].map(function(n){
    return n * 2
}) // [ 2, 4, 6, 8 ]

```

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

# React.js

### Q : What is React? features of React?
A : React is an open-source frontend JavaScript library which is used for building user interfaces especially for single page applications.
* It uses VirtualDOM instead of RealDOM considering that RealDOM manipulations are expensive.
* Supports server-side rendering.
* Follows Unidirectional data flow or data binding.
* Uses reusable/composable UI components to develop the view.
