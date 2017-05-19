[![N|Solid](http://blog.guinatal.com/wp-content/uploads/2015/10/hoisting.jpg)](https://nodesource.com/products/nsolid)
# Executive Summary

 - Hoisting is more of a term used to help understand how JavaScript looks at your code while it is compiling. Hoisting “moves” the declaration to the top of the function/block of code while compiling. This means you are able to use functions before they are made, as it hoisting moves it to the top while compiling the code in the file.

- Variables, functions and constants have a lifecycle which involve three parts:

1) Declaration
2) Initiailization
3) Usage

e.g.
``` 
    var a  -> declaration
        a = 2 -> initialization
    console.log(a) -> usage
```
- Think of it in terms of making a meal. Your fridge would be the code and the ingredients inside would be the functions and variables. Your eyes, the compiler, look through the fridge to find the ingredients for what you want to make.


# Context

Hoisting is a general way of thinking about Javascript's process of execution context, it is a way to explain how Javascript works.  It is something you will not find in the Javascript docs as the action's are often done by the Javascript Interpreter.

Functions, variables and constants in javascripts are all affected by hoisting, whereby the declaration is moved to the top. Hoisting can apply within a function, within a block of code or an application.

# Usage

An example of `Hoisting`:
```js
x = 5;      // Assign 5 to x

elem = document.getElementById("demo");         // Find an element 
elem.innerHTML = x;                             // Display x in the element

var x;      // Declare x
```

In this JavaScript example, a variable can be declared after it has been used. In other words; a variable can be used before it has been declared and this code will still execute.

Basically, the JavaScript interpreter "looks ahead" to find all the variable declarations and "hoists" them to the top of the function. It does not need to do this literally in the code you type into your text editor, so you won't see your code physically change from Hoisting.

Think of it as metaphorically lifting your variables and functions to the top of your code (as is being done behind the scenes).

Only the declaration is hoisted to the top.

[![N|Solid](https://ogmcsrgk5.qnssl.com/13281/826d7a289ef8489b872917570545bdc3.png (154kB) )](https://nodesource.com/products/nsolid)

# Potential Pitfalls

 ``` 
 function hoist() {
  var message;
  console.log(message);
  message='Hoisting is all the rage!'
}
hoist(); // Ouput: undefined
})();
```
The result you’ll get from the above code is **Undefined**  
Since JavaScript hoisting has declared the variables, the main reason why it appeared as undefined is because it wasn’t initialized.
To avoid the pitfall we need to make sure we **declare** and **initialize** the variable.
```
function hoist() {
  var message='Hoisting is all the rage!'
  return (message);
}
hoist(); // Ouput: Hoisting is all the rage!
```

# Resources

- https://developer.mozilla.org/en-US/docs/Glossary/Hoisting
- http://www.i-programmer.info/programming/javascript/5364-javascript-hoisting-explained.html
- https://scotch.io/tutorials/understanding-hoisting-in-javascript
- https://www.w3schools.com/js/js_hoisting.asp
- https://www.sitepoint.com/back-to-basics-javascript-hoisting/
- https://rainsoft.io/javascript-hoisting-in-details/
