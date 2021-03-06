[**REACT**](react.md)


## React Router

**Links**
* [**Navbar Design Examples**](https://www.w3schools.com/css/css_navbar.asp)


### Setup Tutorial For Spa Router.

* **Step 1. Use that snippet for your Controller**

        class App extends Component {
          render() {
            return (
              <BrowserRouter>
              <div>
              <Navigation />
                <Switch>
                //Hera are gonna be our Routes
                <Route path='' component={}/>
                </Switch>
              </div>
              </BrowserRouter>
            );
          }
        }

**Create a component folder, where you can add all your component.js files.**

--- 

* **Step 2. Go to the terminel and add the react router dom, with follwing command:**

        npm add react-router-dom

Check in your project folder under package.json, if the router dependencies is installed.

---

* **Step 3.**
Import the following snippet to the top of your App.js file.

      import { BrowserRouter, Router, Switch } from 'react-router-dom';

The Router takes 2 parameter:
  1. Name of the path.
  
           path='/' (that would be the Home path)
  
  2. 
  
           component= { components Name }
           
**Importent**

Remember to write the command **exact** in your Home Route!!

      <Route path="/" component={Home} exact/>

**exact** just means that it only will render his component if the given url is exactly the same.

---

* **Step 4. Error handling**
Error handling is gonna tell us that the requestet path is not excisting.
  * create an Error.js file.
  * insert a new Route between our Switch tag. 
    
         <Route component={Error} />
  
Route without the path. React will know that the path is none excisting and will show the Error we provide in our Error component.

    import React from 'react';

    const Error = () => {
        return (
            <div>
                <p>Error: Path does not exist!!!</p>
            </div>
        )
    }
    export default Error;
    
---

* **Step 5. Navigation Link.**

* Create navigation.js file
* Import NavLink

      import {NavLink} from 'react-router-dom';


NavLink only takes on one parameter.

    <NavLink to='/Name Of the Component Path'>About</NavLink>

Here you create links for your pages to different url's.

    import React from 'react';
    import { NavLink } from 'react-router-dom';

    const Navigation = () => {
        return (
            <div>
                <NavLink to='/'>Home</NavLink>
                <NavLink to='/about'>About</NavLink>
                <NavLink to='/contact'>Contact</NavLink>
            </div>
        )
    }
    export default Navigation;

---

**Controller Example**

      //React
      import React, { Component } from "react";
      //CSS
      import "./css/App.css";
      //Router
      import { BrowserRouter, Route, Switch } from "react-router-dom";
      //Links
      import About from "./components/About";
      import Contact from "./components/Contact";
      import Error from "./components/Error";
      import Home from "./components/Home";
      import Navigation from "./components/Navigation";

      class App extends Component {
        render() {
          return (
            <BrowserRouter>
            <div>
            <Navigation />
              <Switch>
                <Route path="/" component={Home} exact/>
                <Route path="/about" component={About} />
                <Route path="/contact" component={Contact} />
                <Route component={Error} />
              </Switch>
            </div>
            </BrowserRouter>
          );
        }
      }

      export default App;


















