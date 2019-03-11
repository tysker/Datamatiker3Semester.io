[**HOME**](index.md) - [**Group Review**](groupreview.md)


# Week 6 Group 3 Questions and Answers


## JavaScript Exercises - Tuesday


### Hoisting

**_What is Hoisting?_**

* When Javascript compiles all of the code, all variable declarations using var are hoisted/lifted to the top of their                      functional/local scope (if declared inside a function) or to the top of their global scope (if declared outside of a function)          regardless of where the actual declaration has been made. This is what we mean by “hoisting”.
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
  
### 'this' ind javaScript

**_How this in JavaScript differ from this in Java_**

**JavaScript:**
 Regular function call:
 * The this keyword points at the global object, (the window object in the browser)
  
 Method call :
 * The this variable points to the object that is calling the method.
 * The this keyword is not assigned a value until the function where it is defined is actually called.
 
_This is the window(browser) object. The window object is the default object in JavaScript_

    console.log(this)


_This is a regular function call, so the this keyword still points to the window object_

     calculateAge(1977); //output: 42 and window object

    function calculateAge(year) {
    console.log(2019 - year)
    console.log(this)
     }


_The this variable points to the object that is calling the method. The "john" object_

     var john = {
       name: 'John',
        yearOfBirth: 1977,
        calculateAge: function () {
        console.log(this);
        console.log(2019 - this.yearOfBirth);
       }
      }

john.calculateAge(); //output: john object and 42

_This is a Object with a regular function call. And again the this keyword in the inner Function
points to the global window object._

      var hans = {
          name: 'Hans',
          yearOfBirth: 1977,
          calculateAge: function () {
              console.log(this);
              console.log(2019 - this.yearOfBirth);
              function innerFunction() {
                  console.log(this + "hallo");
              }
              innerFunction();
          }
      }






**Java**
  


##  AJAX with fetch and DOM manipulation Wednesday





