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
