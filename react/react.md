[**HOME**](/index.md)


## React Basics

### New Project

      npx create-react-app nameOfTheProject


### Imports

      import React from 'react';
      import ReactDOM from 'react-dom';
    
    
### Function and Class Components

      function Welcome(props) {
        return <h1>Hello, {props.name}</h1>;
      }
    
* **Note: Always start component names with a capital letter.**

      class Welcome extends React.Component {
                render() {
                  return <h1>Hello, {this.props.name}</h1>;
                    }
                  }



