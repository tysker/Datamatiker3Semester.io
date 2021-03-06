* [**HOME**](../index.md)
* [**REACT ABC**](reactabc.md)  
* [**FUNCTIONS AND COMPONENTS**](functions.md)
* [**STATE AND PROPS**](stateandprops.md)
* [**LIFECYCLE**](lifecycle.md)
* [**REACT ROUTER**](reactrouter.md) 
* [**HANDLING EVENTS**](handlingevents.md)
* [**ERROR HANDLING IN REACT FETCH**](errorhandling.md)
* [**REACT STYLES**](reactstyle.md)
* [**PAGINATION**](pagination.md)
* [**REACT NATIVE**](reactnative.md)
* [**Fetch - Await - Async**](../javascript/promises.md)
* [**AXIOS.js**](axios.md)
* [**REACT QUICK GUIDE**](reactquickguide.md)

### New Project

      npx create-react-app nameoftheproject
      
      
   <a href="https://github.com/facebook/create-react-app/blob/master/README.md" target="-blank">Create React App </a>


### Imports

      import React, { Component } from "react";
      import ReactDOM from 'react-dom';
            
      
## React Basics

* **Note: Always start component names with a capital letter.**
* **Each component needs to return/ render some JSX code - it defines which HTML code React should render to the real DOM in the end.**
* **Components are the core building block of React apps. React is just a library for creating components in its core.**
* **A typical React app therefore could be depicted as a component tree - having one root component ("App") and then an potentially infinite amount of nested child components.**
* **props  and state  are CORE concepts of React. Only changes in props and/or state trigger React to re-render your components and potentially update the DOM in the browser**
* **Parent to Child use prop**
* **Child to Parent use a callback and states**
* **The key word "super" refers to the parent class constructor. You will not be able to use "this" in a constructor until you've called the parent constructor.**
* **We have to pass props in both the constructor og in super, so that the base React.Component constructor can initalize this.props**


## React Components — Three Basic Principles


1. A component should be a pure function which transforms data into a user interface. For a regular React web app, this means that a component takes some data and returns HTML.
   
2. Components should be as generic as possible to promote reusability. To achieve this, you don’t want to bind the components which generate your HTML to a specific state management solution. Instead, you divide your components into container (smart) components and presentational (dumb) components. 
The smart components extract data from your state without directly generating HTML (and thus can be bound to your state management!), while the dumb components transform that data into HTML.

3. A component should be performant. It should only render when its input has changed.  
    
**This code is JSX and not html, and if we would not use JSX, we would have to write the code as shown below**
 
       class App extends Component {
          render() {
               return (
                  <div className="App">
                  <h1>'Hi, I\'m a Reacht App!!!'</h1>
                  </div>
              );
              
              
**This is how JSX is converted to React elements behind the scene:**

         render() {
           return React.createElement('div', {className: 'App'}, React.createElement('h1',null,'Hi, I\'m a Reacht App!!!'));
            }
      }
      
---

## TypeChecking with Prop Types
You can define default values for your props by assigning to the special defaultProps property.

      //Component using props
      function Welcome(props) {
        return <h2>Hello, {props.name}</h2>;
      }
      //Set Type
      Welcome.propTypes = {
        name: PropTypes.string
      }
      //Set Default Value
      Welcome.defaultProps = {
        name: "UNKNOWN"
      }

--- 

* **Describe the term Single Page Application**

A single-page-application are webb aps that loads a single html page and dynamically update as the user interacts with the app. SPA's use AJAX and HTML5 to create fluid and responsive Web apps, without constant page reloads. This means much of the work happens on the clients side, in JavaScript. 

**Why are SPA's are so popular?**

* SPA's are fast, as most ressourcess (HTML+CSS+Scripts) are only loaded once throughout the lifespan of the application. Only data is transmitted back and forward. 
* Development for SPA's are simplified and much easier to deploy. There is no need to write code to render pages on the server. 
* SPA's are easy to debug with Chrome, as you can monitor network operations, investigate page elements and data associated with it. If you use React for develop your application, you can also use Google's Chrome React extendsion to investigate your React/JSX code iven further.
* It is easier to make mobile apps.
* SPA can cache any data localy on your computer, so you application could even work offline.

**The "recommended" React way of passing data into Components.**
The recommend way to pass data in React is from top til bottom. It is also commen that Parent components pass data down to nested Child components with props.

* **What is the Observer pattern?**


/ answer is missing /

<img src="../images/spa.png" width="400"/>


    
    



