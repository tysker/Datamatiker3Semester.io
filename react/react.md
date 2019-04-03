[**HOME**](/index.md)


## React Basics

* **Note: Always start component names with a capital letter.**
* **Each component needs to return/ render some JSX code - it defines which HTML code React should render to the real DOM in the end.**
* **Components are the core building block of React apps. React is just a library for creating components in its core.**
* **A typical React app therefore could be depicted as a component tree - having one root component ("App") and then an potentially infinite amount of nested child components.**
* **props  and state  are CORE concepts of React. Only changes in props and/or state trigger React to re-render your components and potentially update the DOM in the browser**


### When creating components, you have the choice between two different ways:

1. Functional components (also referred to as "presentational", "dumb" or "stateless" components.

        const cmp = () => { return <div>some JSX</div> }

2. class-based components (also referred to as "containers", "smart" or "stateful" components).

        class Cmp extends Component { render () { return <div>some JSX</div> } }
        
    
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


### New Project

      npx create-react-app nameOfTheProject


### Imports

      import React from 'react';
      import ReactDOM from 'react-dom';
    
    
### Function and Class Components

      function Welcome(props) {
        return <h1>Hello, {props.name}</h1>;
      }
    
      class Welcome extends React.Component {
        render() {
          return <h1 > Hello, {
            this.props.name
          } < /h1>;
        }
      }

**S**
* **state** = Whilst props allow you to pass data down the component tree (and hence trigger an UI update), state is used to change the component, well, state from within. Changes to state also trigger an UI update.Only class-based components can define and use state . You can of course pass the state  down to functional components, but these then can't directly edit it.

**P**
* **probs** = allow you to pass data from a parent(wrapping) component to a child (embedded) component.
