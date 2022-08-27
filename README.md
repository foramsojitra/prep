<!-- [Javascript](#javascript "Goto Javascript") -->
<!-- [Node.js](#Node.js "Goto Node.js") -->

# Javascript

### Q : What is js?
A : JavaScript is a programming language commonly used in web development. It was originally developed by Netscape as a means to add dynamic and interactive elements to websites.
JavaScript is a synchronous, blocking, single-threaded language.
JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during run-time in contrast to statically typed language, where the type of a variable is checked during compile-time.

JavaScript is a dynamically typed language. In a dynamically typed language, the type of a variable is checked during run-time in contrast to statically typed language, where the type of a variable is checked during compile-time

### Q : What are the possible ways to create objects in JavaScript
A : 
1. Object constructor:
```var object = new Object();```

2. Object's create method:
```var object = Object.create(null);```

3. Object literal syntax:
```var object = {
     name: "Sudheer"
     age: 34
};```

4. Function constructor:
```function Person(name) {
  this.name = name;
  this.age = 21;
}
var object = new Person("Sudheer");```

5. Function constructor with prototype:
```function Person() {}
Person.prototype.name = "Sudheer";
var object = new Person();```

6. ES6 Class syntax
```class Person {
  constructor(name) {
    this.name = name;
  }
}

var object = new Person("Sudheer");``` 

### Q : Difference between "var", "let" and "const"
A : 
var	let	const
The scope of a var variable is functional scope.	   The scope of a let variable is block scope.	     The scope of a const variable is block scope.
It can be updated and re-declared into the scope.	  It can be updated but cannot be re-declared into the scope.	It cannot be updated or re-declared into the scope.
It can be declared without initialization.	It can be declared without initialization.	It cannot be declared without initialization.
It can be accessed without initialization as its default value is “undefined”.	It cannot be accessed without initialization, as it returns an error.	It cannot be accessed without initialization, as it cannot be declared without initialization.

var is there from the begining of the js, let and const introduced in ES6 all of this can be used for variable declaration. 
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

### Q : JS array method
A : 
The pop() method removes the last element from an array. The pop() method returns the value that was "popped out".

The push() method adds a new element to an array (at the end).The push() method returns the new array length.

The shift() method removes the first array element and "shifts" all other elements to a lower index.The shift() method returns the value that was "shifted out".

The unshift() method adds a new element to an array (at the beginning), and "unshifts" older elements.The unshift() method returns the new array length.

The concat() method creates a new array by merging (concatenating) existing arrays, The concat() method does not change the existing arrays. It always returns a new array.The concat() method can take any number of array arguments.

Splicing and Slicing Arrays :
The splice() method can be used to add new items to an array

```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
fruits.splice(2, 0, "Lemon", "Kiwi");
```
The first parameter (2) defines the position where new elements should be added (spliced in).

The second parameter (0) defines how many elements should be removed.

The rest of the parameters ("Lemon" , "Kiwi") define the new elements to be added.

The splice() method returns an array with the deleted items:

The slice() method slices out a piece of an array into a new array.

This example slices out a part of an array starting from array element 1 ("Orange"):

The slice() method creates a new array.

The slice() method does not remove any elements from the source array.

### Q : What is scope in javascript
A : Scope is the accessibility of variables, functions, and objects in some particular part of your code during runtime. In other words, scope determines the visibility of variables and other resources in areas of your code.

### Q : What is a first order function
A : First-order function is a function that doesn’t accept another function as an argument and doesn’t return a function as its return value.

```const firstOrder = () => console.log ('I am a first order function!');```

### Q : What is a strict mode in javascript
A : Strict Mode is a new feature in ECMAScript 5 that allows you to place a program, or a function, in a “strict” operating context. This way it prevents certain actions from being taken and throws more exceptions. The literal expression "use strict"; instructs the browser to use the javascript code in the Strict mode.

### Q : Different Types of Loops in JavaScript
A : 
* while — loops through a block of code as long as the condition specified evaluates to true.
```
while (i < 10) {
  text += "The number is " + i;
  i++;
}
```

* do…while — loops through a block of code once; then the condition is evaluated. If the condition is true, the statement is repeated as long as the specified condition is true.
```
do {
  text += "The number is " + i;
  i++;
}
while (i < 10);
```

* for — loops through a block of code until the counter reaches a specified number.
```
for (let i = 0; i < cars.length; i++) {
  text += cars[i] + "<br>";
}
```

* for…in — loops through the properties of an object.
```
for (key in object) {
  // code block to be executed
}
```

* for…of — loops over iterable objects such as arrays, strings, etc.
```
let text = "";
for (let x of cars) {
  text += x;
}
```

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

 JavaScript non-primitive data types : 
    Object, Array, RegExp
~~~
The difference between primitives and non-primitives is that primitives are immutable and non-primitives are mutable.

Non primitive values can also be referred to as reference types because they are being compared by reference instead of value. Two objects are only strictly equal if they refer to the same underlying object.

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

=== is faster than ==

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
### Q : Explain “this” keyword
A : The “this” keyword refers to the object that the function is a property of.
The value of “this” keyword will always depend on the object that is invoking the function.

```
var obj = {
    name:  "vivek",
    getName: function(){
    console.log(this.name);
  }
}
        
obj.getName();
```

### Q : What would be the result of 3+2+"7"?
A : Since 3 and 2 are integers, they will be added numerically. And since 7 is a string, its concatenation will be done. So the result would be 57.

### Q : What is type of null and function?
A : type of null is "object" and type of function is "function".

### Q : What is closure and counter dillema?
A : We can create nested functions in JavaScript. Inner function can access variables and parameters of an outer function (however, cannot access arguments object of outer function).
A JavaScript closure is when an inner function has access to its outer enclosing function's variables and properties. like bwlow example.


Closures help in maintaining the state between function calls without using a global variable.

Closures are frequently used in JavaScript for object data privacy, in event handlers and callback functions, and in partial applications, currying, and other functional programming patterns
```
javascript
function OuterFunction() {

    var outerVariable = 1;

    function InnerFunction() {
        console.log(outerVariable);
    }

    InnerFunction();
    //or
    // return InnerFunction
}
OuterFunction()
//or
//OuterFunction()();
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

### Q : What is a prototype chain?
A : Prototype chaining is used to build new types of objects based on existing ones. It is similar to inheritance in a class based language.

The prototype on object instance is available through Object.getPrototypeOf(object) or proto property whereas prototype on constructors function is available through Object.prototype.


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
A : Callback: Callback is an asynchronous equivalent for a function. A callback function is called at the completion of a given task.  callback is a function that will be executed after another function gets executed.
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
### Q : What are the pros and cons of promises over callbacks? 
A : Below are the list of pros and cons of promises over callbacks,

Pros:

It avoids callback hell which is unreadable
Easy to write sequential asynchronous code with .then()
Easy to write parallel asynchronous code with Promise.all()
Solves some of the common problems of callbacks(call the callback too late, too early, many times and swallow errors/exceptions)
Cons:

It makes little complex code
You need to load a polyfill if ES6 is not supported

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
```
javascript
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
```
javascript
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
```
javascript
const double = n => n * 2
[1, 2, 3, 4].map(double) // [ 2, 4, 6, 8 ]
--- OR ---
[1, 2, 3, 4].map(function(n){
    return n * 2
}) // [ 2, 4, 6, 8 ]

```
### Q : What is DOM?
A : DOM stands for Document Object Model.

DOM is a programming interface for HTML and XML documents.

When the browser tries to render a HTML document, it creates an object based on the HTML document called DOM. Using this DOM, we can manipulate or change various elements inside the HTML document.


### Q : What is the rest parameter and spread operator?
A : Both rest parameter and spread operator were introduced in the ES6 version of javascript.

Rest parameter ( … )

It provides an improved way of handling parameters of a function.

Using the rest parameter syntax, we can create functions that can take a variable number of arguments.

Any number of arguments will be converted into an array using the rest parameter.

It also helps in extracting all or some parts of the arguments.

Rest parameter can be used by applying three dots (...) before the parameters.

```
function extractingArgs(...args){
  return args[1];
}

// extractingArgs(8,9,1); // Returns 9

function addAllArgs(...args){
  let sumOfArgs = 0;
  let i = 0;
  while(i < args.length){
    sumOfArgs += args[i];
    i++;
  }
  return sumOfArgs;
}

addAllArgs(6, 5, 7, 99); // Returns 117
addAllArgs(1, 3, 4); // Returns 8
```
- Rest parameter should always be used at the last parameter of a function:

Spread operator (…)

Although the syntax of spread operator is exactly the same as the rest parameter, spread operator is used to spread an array, and object literals. We also use spread operators where one or more arguments are expected in a function call.

```
function addFourNumbers(num1,num2,num3,num4){
  return num1 + num2 + num3 + num4;
}

let fourNumbers = [5, 6, 7, 8];


addFourNumbers(...fourNumbers);
// Spreads [5,6,7,8] as 5,6,7,8

let array1 = [3, 4, 5, 6];
let clonedArray1 = [...array1];
// Spreads the array into 3,4,5,6
console.log(clonedArray1); // Outputs [3,4,5,6]
```

### Q : What is Object Destructuring?

A : Object destructuring is a new way to extract elements from an object or an array.

```
const classDetails = {
  strength: 78,
  benches: 39,
  blackBoard:1
}

const {strength:classStrength, benches:classBenches,blackBoard:classBlackBoard} = classDetails;

console.log(classStrength); // Outputs 78
console.log(classBenches); // Outputs 39
console.log(classBlackBoard); // Outputs 1
```

### Q : What are the falsy values in JavaScript?
A : '', 0, null
undefined
false
NaN

### Q : How to check if a value is falsy?
A : Use the !! operator or Boolean function to check if they’re falsy.
If a value is falsy, then both will return false.

!!0
false

### https://stackoverflow.com/questions/17502948/nexttick-vs-setimmediate-visual-explanatio

### Q : Debouncing and Throttling in JavaScript
A : DEBOUNCING
Debounce function limits the execution of a function call and waits for a certain amount of time before running it again.

Debouncing is a programming practice used to ensure that time-consuming tasks do not fire so often, that it stalls the performance of the web page. The debounced function will ignore all calls to it until the calls have stopped for a specified time period. Only then will it call the original function.
Debouncing forces a function to wait a certain amount of time before running again. In other words, it limits the rate at which a function gets invoked.

Implementing Debounce:
The general idea for debouncing is-
1) Start with 0 timeout.
2) If the debounced function is called again, reset the timer to the specified delay.
3) In case of timeout, call the debounced function.
Thus every call to a debounce function resets the timer and delays the call.

```
const debounce = function(func, delay){
      let timer;
      return function () {     //anonymous function
        const context = this; 
	const args = arguments;
	clearTimeout(timer); 
	timer = setTimeout(()=> {
	    func.apply(context, args)
	},delay);
       }
}
```

Throttling

Throttling or sometimes is also called throttle function is a practice used in websites. To throttle a function means to ensure that the function is called at most once in a specified time period (for instance, once every 10 seconds). This means throttling will prevent a function from running if it has run “recently”. Throttling also ensures a function is run regularly at a fixed rate.
Throttling is used to call a function after every millisecond or a particular interval of time only the first click is executed immediately.

Implementing Throttle:
Throttle can be a little taxing as its desired behavior has different interpretations. Let’s start by limiting the rate at which we execute a function.
Gaming — In action games, the user often performs a key action by pushing a button (example: shooting, punching). But, as any gamer knows, users often press the buttons much more than is necessary, probably due to the excitement and intensity of the action. So the user might hit “Punch” 10 times in 5 seconds, but the game character can only throw one punch in one second. In such a situation, it makes sense to throttle the action. In this case, throttling the “Punch” action to one second would ignore the second button press each second.

Scroll event handler — Another application of throttling is in content-loading webpages like Facebook and Twitter where the user keeps on scrolling. In these scenarios, if the scroll event is fired too frequently, there might be a performance impact, as it contains lots of videos and images. Thus the scroll event must make use of throttling.

1. Throttling a button click so we can’t spam click
2. Throttling an API call
3. Throttling a mousemove/touchmove event handler
~~~
1) Debouncing is a technique where we can monitor the time delay of user action and once that delay reaches our predetermined threshold we can can make the function call.

2) Throttling is a technique where we make the function call in a predetermined time interval irrespective of continuous user actions.

3) Even though both debouncing and throttling seems like similar, both have their own use-cases. It’s not recommended to use throttling logic in search bar and we we cannot use debouncing in shooting game scenario or browser resizing or onScroll events.

Throttling or sometimes is also called throttle function is a practice used in websites. Throttling is used to call a function after every millisecond or a particular interval of time only the first click is executed immediately.


### Q : call, apply and bind in JavaScript
A : 
```
var obj = {
 num: 2
}

var add = function(a,b,c){
 return this.num + a + b + c
}

add.call(obj, 1,2,3)
add.apply(obj, [1,2,3])
var bound = add.bind(obj)
bound(1,2,3)
```

* call method invokes the function with 1st argument as context object and further comma separated arguments which the function can directly consume.
* apply is exactly same as call method, the only difference is it takes the 2nd argument as array list of the parameters.
* bind method is similar to the call method but it does not invokes the function, rather gives you the copy of exactly same function, which can be invoked later.

where it's used

 apply() when you want to invoke the function immediately, and modify the context. Call/apply call the function immediately, whereas bind returns a function that, when later executed, will have the correct context set for calling the original function.

The call, bind and apply methods can be used to set the this keyword independent of how a function is called. The bind method creates a copy of the function and sets the this keyword, while the call and apply methods sets the this keyword and calls the function immediately.



