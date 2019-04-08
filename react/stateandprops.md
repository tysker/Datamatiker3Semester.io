[**REACT**](react.md)


_"The main responsibility of a component is to translate raw data into rich HTML."_

## State and Props

* **Could you use or change state in an functional component?**
No, functional components are stateless components. You will not be able to setState in your method.

* **Where do you use setState and state?
You will set **state** only in your constructor where **setState()** can be used in any functions but not in the constructor.

* **How is it possible to tell React that you want to the UI to be updated (re-rendered)?
A re-render can only be triggered if a component's state has changed. The state can change from a **props** change, or from a direct **setState** change. The component will get the update change and will then decide to re-render the DOM.

* **How do you pass in prop values to a Component?**
Every child components gets its props from the parent. In a function component, props is all it gets passed, and they are available by adding props as the function argument.

      const BlogPostExcerpt = props => {
        return (
          <div>
            <h1>{props.title}</h1>
            <p>{props.description}</p>
          </div>
        )
      }
      
In a class component, props are passed by default. There is no need to add anything special, and they are accessible as this.props in a Component instance.

import React, { Component } from 'react'

      class BlogPostExcerpt extends Component {
        render() {
          return (
            <div>
              <h1>{this.props.title}</h1>
              <p>{this.props.description}</p>
            </div>
          )
        }
      }


* **What is the different between state and props?**

_"a component manages its own state, but the properties are given by its predecessor"._

_Most of the components should simply take some data from props and render it. However, sometimes you need to respond to user input, a server request or the passage of time. For this you use state._

* **props**
    * are variables passed to it by it's parent component.
    * will be able to use or not the properties given by his "father" but it will not be able to modify them.
    * **Stateless component:** It only has the props. It is not very interactive, basically it has the function of render () and little else.


* **state**
    * are variables directly initialized and managed by the component.
    * a state can be changed
    * **Stateful component:** It has both the props and the state. These components are those that interact with the server, react to user events, etc.


* **In commen**
    * Both are JavaScript objects
    * Both are _triggers_ to render a component (when there is a change in one of them, the component is rendered again).
    * As long as the entry of props and state doesn't change, the result will always be the same.
