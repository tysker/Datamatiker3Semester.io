[**HOME**](/index.md)


## React Basics

* **Note: Always start component names with a capital letter.**
* **Each React component has to return and render JSX code**

    
 This code is jpx and not html, if we would not use jpx we would have to write like the code below 
 
       class App extends Component {
          render() {
               return (
                  <div className="App">
                  <h1>'Hi, I\'m a Reacht App!!!'</h1>
                  </div>
              );
              
              
This is how jpx is compiled behind the scene:

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



