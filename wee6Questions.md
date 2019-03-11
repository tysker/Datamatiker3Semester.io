[**HOME**](index.md) - [**Group Review**](groupreview.md)


# Week 6 Group 3 Questions and Answers


## JavaScript Exercises - Day-1


### Hoisting

**_What is Hoisting?_**

* When Javascript compiles all of the code, all variable declarations using var are hoisted/lifted to the top of their                       functional/local scope (if declared inside a function) or to the top of their global scope (if declared outside of a function)             regardless of where the actual declaration has been made. This is what we mean by “hoisting”.
* You can declare a variable after it has been used;
* All declarations (var, let, const, function, function*, class) are "hoisted" in JavaScript.
  The difference between var, let and const declarations is its initialisation. instances of var are initialised with undefined while let   and const will throw a Reference error if you try to call one before it has been assigned a value.

**_A design rule we could follow, now we know about hoisting_**

* Always declare all variables at the beginning of every scope.

**_What is the difference between the keyword var and the ES6 keyword let?_**

* Var is function based. It means you can use the variables in the whole function.
  const and let is block based. You can't use them outside of the block.
  In const and let you have to declare them outside of the block
  const you have to define outside of the block.





