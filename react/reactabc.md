[**REACT**](react.md)

## REACT ABC

**C**
* **Components** = Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.
* **constructor** = The constructor for a React component is called before it is mounted. When implementing the constructor for a React.Component subclass, you should call super(props) before any other statement. Otherwise, this.props will be undefined in the constructor, which can lead to bugs. 
Constructor is the only place where you should assign this.state directly. In all other methods, you need to use this.setState() instead.
It is used for mostly only two purposes:
1. Initializing local state by assigning an object to this.state.
2. Binding event handler methods to an instance.

**F**
* **Fragments** = <a href="https://reactjs.org/docs/fragments.html" target="_blank">React Home</a>

**I**
* [**Id**](https://www.npmjs.com/package/uuid) = To regnerate an Id import:  _import uuid from 'uuid';_ and implement it like that: _id=uuid.c4()_

**K**
* **Keys** = Keys help React identify which items have changed, added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity.

**J**
* **JSX** = (JavaScript XML) JSX is a syntax extension til JavaScript.

**R**
* **React**
* **render** = The render() method is the only required method in a class component.
When called, it should examine this.props and this.state and return one of the following types:
  1. **React elements.** Typically created via JSX. For example, \<div /\> and \<MyComponent /\> are React elements that instruct React to render a DOM node, or another user-defined component, respectively.
  2. **Arrays and fragments.** Let you return multiple elements from render.
  3. **Portals.** Let you render children into a different DOM subtree.
  4. **String and numbers.** These are rendered as text nodes in the DOM.
  5. **Booleans or null.** Render nothing. (Mostly exists to support return test && \<Child /\> pattern, where test is boolean.)

**S**
* **state** = Whilst props allow you to pass data down the component tree (and hence trigger an UI update), state is used to change the component, well, state from within. Changes to state also trigger an UI update.Only class-based components can define and use state . You can of course pass the state  down to functional components, but these then can't directly edit it.
**Avoid copying props into state!**
* **super()** = to call the constructor function that is inherit from React.Component

**L**
* **Linebreak in tabels JSX** = 

        <th>{country.timezones.map( (zones,index) => <span>{zones}<br/></span>)}</th>

**M**
* **mounting** = 

**N**

**P**
* **probs** = allow you to pass data from a parent(wrapping) component to a child (embedded) component.
* **portals** = <a href="https://reactjs.org/docs/portals.html" target="_blank">React Home</a>

**U**
* **unmounting** = 
