[**REACT**](react.md)

## Reacts Lifecycle

<img src="../images/lifecycle.jpg" width="800"/> 

### What is the purpose of React Components Life Cycle Methods?

To update the DOM!

### What is the Life Cycle methods in React?

A component's lifecycle is broadly classified into four parts:
* initialization
* mounting
* updating, and
* unmounting

**Initialization**
This is the phase in which the component is going to start its journey by setting up the state and the props. This is usually done inside the constructor method.

**Mounting**
Mounting is the phase in which our React component mounts on the DOM.

1. componentWillMount()
This method is called just before a component mounts on the DOM or the render method is called. After this method, the component gets mounted.

2. componentDidMount()
This method is called after the component gets mounted on the DOM. Like componentWillMount, it is called once in a lifecycle. Before the execution of this method, the render method is called (i.e., we can access the DOM). We can make API calls and update the state with the API response.

**Updating**
This is where component’s state changes and hence, re-rendering takes place.

In this phase, the data of the component (state & props) updates in response to user events like clicking, typing and so on. This results in the re-rendering of the component. The methods that are available in this phase are:

1. shouldComponentUpdate()
This method determines whether the component should be updated or not. By default, it returns true. But at some point, if you want to re-render the component on some condition, then shouldComponentUpdate method is the right place.

2. componentWillUpdate()
It is called before the re-rendering of the component takes place. It is called once after the ‘shouldComponentUpdate’ method. If you want to perform some calculation before re-rendering of the component and after updating the state and prop, then this is the best place to do it.

3. ComponentDidUpdate()
This method is called just after the re-rendering of the component. After the new (updated) component gets updated on the DOM, the ‘componentDidUpdate’ method is executed. This method receives arguments like prevProps and prevState.

**Unmounting**
This is the last phase in the component’s lifecycle. As the name clearly suggests, the component gets unmounted from the DOM in this phase. The method that is available in this phase is:

1.  componentWillUnmount()
This method is called before the unmounting of the component takes place. Before the removal of the component from the DOM, ‘componentWillUnMount’ executes. This method denotes the end of the component’s lifecycle.

