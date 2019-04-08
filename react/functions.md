[**REACT**](./react.md)


## Function and Class Components

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


### When creating components, you have the choice between two different ways:

1. Functional components (also referred to as "presentational", "dumb" or "stateless" components.

        const cmp = () => { return <div>some JSX</div> }

2. class-based components (also referred to as "containers", "smart" or "stateful" components).

        class Cmp extends Component { render () { return <div>some JSX</div> } }
        
        
### What is a functional component?

Functional Components are accepting properties or props as an argument and then returning valid JSX. 

The key thing that makes this type of component different from a class component is the lack of state and lifecycle methods. This is why functional components are also commonly referred to as stateless components.
(you can't use state or setState()!)


### Why should I use functional components at all?

1. Functional component are much easier to read and test because they are plain JavaScript functions without state or lifecycle-hooks
2. You end up with less code
3. They help you to use best practices. It will get easier to separate container and presentational components because you need to think    more about your component’s state if you don’t have access to setState() in your component
4. The React team mentioned that there may be a performance boost for functional component in future React versions



### What is a Class component?

A Class component requires to extend from React.Component. You be able to use state or lifecycle hooks.


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

