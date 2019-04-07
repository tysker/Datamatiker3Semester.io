[**HOME**](/index.md) - [**REACT ABC**](reactabc.md) - [**Functions And Components**](functions.md)

### New Project

      npx create-react-app nameOfTheProject
      
      
   <a href="https://github.com/facebook/create-react-app/blob/master/README.md" target="-blank">Create React App </a>


### Imports

      import React from 'react';
      import ReactDOM from 'react-dom';
            
      
## React Basics

* **Note: Always start component names with a capital letter.**
* **Each component needs to return/ render some JSX code - it defines which HTML code React should render to the real DOM in the end.**
* **Components are the core building block of React apps. React is just a library for creating components in its core.**
* **A typical React app therefore could be depicted as a component tree - having one root component ("App") and then an potentially infinite amount of nested child components.**
* **props  and state  are CORE concepts of React. Only changes in props and/or state trigger React to re-render your components and potentially update the DOM in the browser**



        
    
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



    
    



