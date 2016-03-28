Functional Programming
======================

Purpose:
1. Higher order function (e.g., map/redue)
2. Avoid side effect (data goes in, return value goes out)
3. Referential transparent

Concept:
1. Pure functions: easy to test, no side effect, referential transparent
2. Immutability (e.g., string and numbers): Referential transparent
3. Lazy evaluation

Higher Order Functions:
1. First-class functions
  - Function Declaration:
  ```javascript
    function helloWorld(){
      return "Hello";
    }
    ```
    
  - Function Expresion
  ```javascript
    var hello = function helloWorld(){
    return "Hello";
  }
  ```
  
  - Function as a Object Method
  ```javascript
  var person = {
    sayHello: function() {
      console.log("Well, hello");
    }
  }
  ```
  
2. Passing functions as arguments
