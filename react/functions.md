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

## Why should I use functional components at all?

1. Functional component are much easier to read and test because they are plain JavaScript functions without state or lifecycle-hooks
2. You end up with less code
3. They help you to use best practices. It will get easier to separate container and presentational components because you need to think    more about your component’s state if you don’t have access to setState() in your component
4. The React team mentioned that there may be a performance boost for functional component in future React versions




### What is a Class component?

A Class component requires to extend from React.Component. You be able to use state or lifecycle hooks.

