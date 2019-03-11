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
  
 ______
 
  
### "this" keyword in JavaScript



**_How "this" keyword in JavaScript differ from "this" in Java_**

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



**Java:**

* Keyword 'THIS' in Java is a reference variable that refers to the current object.
* It can be used to refer current class instance variable
* It can be used to invoke or initiate current class constructor
* It can be passed as an argument in the method call
* It can be passed as argument in the constructor call
* It can be used to return the current class instance
* "this" is a reference to the current object, whose method is being called upon.
* You can use "this" keyword to avoid naming conflicts in the method/constructor of your instance/object.
  

## The purpose of the methods call(), apply() and bind()

**_The different between call() and apply()_**

**Note:** While the syntax of apply() function is almost identical to that of call(), the fundamental difference is that call() 
accepts an argument list, while apply() accepts a single array of arguments.

**call()**

call() provides a new value of this to the function/method. With call, you can write a method once and then inherit it in another object, without having to rewrite the method for the new objec
The call() allows for a function/method belonging to one object to be assigned and called for a different object.
In this case the object Product is assigned and called from the Food object.

    function Product(name, price) {
        this.name = name;
        this.price = price;
    }

    function Origin(countryOfOrigin) {
        this.countryOfOrigin = countryOfOrigin;
    }
    //this points to the object Product
    function Food(name, price, countryOfOrigin) {
        Product.call(this, name, price);
        Origin.call(this, countryOfOrigin);
        //this.
    }
    var milch = new Food("Milch", 10, "Germany");

    console.log(new Food('cheese', 5, "Turkey").name);
    console.log(milch);
    
    
**apply()**
   
The apply() method calls a function with a given this value, and arguments provided as an array (or an array-like object).

Using apply to append an array to another

    var array = ['a', 'b'];
    var elements = [0, 1, 2];
    array.push.apply(array, elements);
    console.info(array); // ["a", "b", 0, 1, 2]

**bind()**

The bind() method creates a new function that, when called, has its this keyword set to the provided value, with a given sequence of arguments preceding any provided when the new function is called.


      var module = {
          x: 42,
          getX: function () {
              return this.x;
          }
      }

      var unboundGetX = module.getX;
      console.log(unboundGetX()); // The function gets invoked at the global scope
      // expected output: undefined

      var boundGetX = unboundGetX.bind(module);
      console.log(boundGetX());
      // expected output: 42
      
      
______



##  AJAX with fetch and DOM manipulation Wednesday


**_Same Origin Policy governs when and where Ajax request is allowed through. Where in the browser can you get see if the request is allowd or not.** 

Open developer tools in browser. The Response header shows what kind of access is allowed outside:

Access-Control-Allow-Headers:
Content-Type _Which type of content that can be extracted/manipulated_
Access-Control-Allow-Methods: GET _Which CRUD methods are allowed_
Access-Control-Allow-Origin: * //Who can access it. (All)


**_Explain Same Origin Policy_**

The same-origin policy is an important concept in the web application security model. Under the policy, a browser permits scripts from the first web page to access data in a second web page, but only if both web pages have the same origin. An origin is defined as a combination of URI scheme, host name, and port number. This policy prevents a malicious script on one page from obtaining access to sensitive data on another web page through that page's Document Object Model.

____


## JavaScript, DOM, AJAX, CORS and SVG Exam Preperation 1


* Explain about the Object Model, and why it’s (very) relevant for modern Web-development
* Explain (using an example of your own choice) about JavaScript events, and Event Bubbling
* Elaborate on how JSON or XML supports communication between subsystems, even when the subsystems are implemented on diﬀerent platforms.
* Explain the topic AJAX and how it has changed the way modern web-applications are created
* Explain the Same Origin Policy (for AJAX), and different ways to work around it



____


## JavaScript, DOM, JSON, AJAX and JPA Exam Preperation 2


* Explain about the Document Object Model, and why it’s extremely relevant for modern Web-development
* Explain how JavaScript fit’s into modern Web Development
* Explain (using an example of your own choice) about JavaScript events, and Event Bubbling
* Explain (in words) the purpose of the JavaScript-arrays filter and map methods (also, provide a few  examples)
* Explain the topics AJAX and how it has changed the way modern web-applications are created
* Elaborate on how JSON or XML supports communication between subsystems, even when the subsystems are implemented on diﬀerent platforms.





