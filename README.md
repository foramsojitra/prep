# Javascript

### Q : What is js?
A : JavaScript is a programming language commonly used in web development. It was originally developed by Netscape as a means to add dynamic and interactive elements to websites.JavaScript is a synchronous, blocking, single-threaded language.

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
