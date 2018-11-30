<h2>It is React Tutorial.</h2>

https://goo.gl/JEXyeU  <ENG.VER>


https://goo.gl/tdXgs1 <KOR.VER>

# React

<h2>React (JavaScript library)</h2>

In computing, React (also known as React.js or ReactJS) is a JavaScript library for building user interfaces. It is maintained by Facebook and a community of individual developers and companies.

React can be used as a base in the development of single-page or mobile applications. Complex React applications usually require the use of additional libraries for state management, routing, and interaction with an API

<h2>History</h2>
React was created by Jordan Walke, a software engineer at Facebook. He was influenced by XHP, an HTML component framework for PHP. It was first deployed on Facebook's newsfeed in 2011 and later on Instagram.com in 2012. It was open-sourced at JSConf US in May 2013.

React Native, which enables native Android, iOS, and UWP development with React, was announced at Facebook's React.js Conf in February 2015 and open-sourced in March 2015.

On April 18, 2017, Facebook announced React Fiber, a new core algorithm of React framework library for building user interfaces. React Fiber was to become the foundation of any future improvements and feature development of the React framework.[needs update]

Basic usage
The following is a rudimentary example of React usage in HTML with JSX and JavaScript.

<div id="myReactApp"></div>

<script type="text/babel">
  class Greeter extends React.Component { 
    render() { 
      return <h1>{this.props.greeting}</h1>
    } 
  } 

  ReactDOM.render(<Greeter greeting="Hello World!" />, document.getElementById('myReactApp'));
</script>
The Greeter class is a React component that accepts a property greeting. The ReactDOM.render method creates an instance of the Greeter component, sets the greeting property to 'Hello World' and inserts the rendered component as a child element to the DOM element with id myReactApp.

When displayed in a web browser the result will be

<div id="myReactApp">
  <h1>Hello World!</h1>
</div>
Notable features
One-way data binding with props
Properties (commonly, props) are passed to a component from the parent component. Components receive props as a single set of immutable values[13] (a JavaScript object).

Stateful components
States hold values throughout the component and can be passed to child components through props:

class ParentComponent extends React.Component {
  state = { color: 'red' };
  render() {
    return (
      <ChildComponent color={this.state.color} />
    );
  }
}
Virtual DOM
Another notable feature is the use of a "virtual Document Object Model", or "virtual DOM". React creates an in-memory data structure cache, computes the resulting differences, and then updates the browser's displayed DOM efficiently. This allows the programmer to write code as if the entire page is rendered on each change, while the React libraries only render subcomponents that actually change.

<h2>Lifecycle methods</h2>
Lifecycle methods are hooks which allow execution of code at set points during the component's lifetime.

shouldComponentUpdate allows the developer to prevent unnecessary re-rendering of a component by returning false if a render is not required.
componentDidMount is called once the component has 'mounted' (the component has been created in the user interface, often by associating it with a DOM node). This is commonly used to trigger data loading from a remote source via an API.
render is the most important lifecycle method and the only required one in any component. It is usually called every time the component's state is updated, reflecting changes in the user interface.
<h2>JSX</h2>
JSX (JavaScript eXtension) is an extension to the JavaScript language syntax. Similar in appearance to HTML, JSX provides a way to structure component rendering using syntax familiar to many developers. React components are typically written using JSX, although they do not have to be (components may also be written in pure JavaScript). JSX is similar to another extension syntax created by Facebook for PHP, XHP.

An example of JSX code:

class App extends React.Component {
  render() {
    return (
      <div>
        <p>Header</p>
        <p>Content</p>
        <p>Footer</p>
      </div>
    );
  }
}
<h2>Nested elements</h2>
Multiple elements on the same level need to be wrapped in a single container element such as the <div> element shown above, or returned as an array.

<h2>Attributes</h2>
JSX provides a range of element attributes designed to mirror those provided by HTML. Custom attributes can also be passed to the component. All attributes will be received by the component as props.

<h2>JavaScript expressions</h2>
JavaScript expressions (but not statements) can be used inside JSX with curly brackets {}:

  <h1>{10+1}</h1>
The example above will render

  <h1>11</h1>
<h2>Conditional statements</h2>
If–else statements cannot be used inside JSX but conditional expressions can be used instead. The example below will render { i === 1 ? 'true' : 'false' } as the string 'true' because i is equal to 1.

class App extends React.Component {
  render() {
    const i = 1;
    return (
      <div>
        <h1>{ i === 1 ? 'true' : 'false' }</h1>
      </div>
    );
  }
}
Functions and JSX can be used in conditionals:

class App extends React.Component {
  render() {
    const sections = [1, 2, 3];
    return (
      <div>
        { 
          sections.length > 0
            ? sections.map(n => <div>Section {n}</div>)
            : null
        }
      </div>
    );
  }
}
The above will render:

<div>
  <div>Section 1</div>
  <div>Section 2</div>
  <div>Section 3</div>
</div>
Code written in JSX requires conversion with a tool such as Babel before it can be understood by web browsers.This processing is generally performed during a software build process before the application is deployed.

<h2>Architecture beyond HTML</h2>
The basic architecture of React applies beyond rendering HTML in the browser. For example, Facebook has dynamic charts that render to <canvas> tags,[19] and Netflix and PayPal use universal loading to render identical HTML on both the server and client.

<h2>Common idioms</h2>
React does not attempt to provide a complete 'application framework'. It is designed specifically for building user interfaces and therefore does not include many of the tools some developers might consider necessary to build an application. This allows the choice of whichever libraries the developer prefers to accomplish tasks such as performing network access or local data storage. Common patterns of usage have emerged as the library matures.

<h2>Use of the Flux architecture</h2>
To support React's concept of unidirectional data flow (which might be contrasted with AngularJS's bidirectional flow), the Flux architecture represents an alternative to the popular model-view-controller architecture. Flux features actions which are sent through a central dispatcher to a store, and changes to the store are propagated back to the view. When used with React, this propagation is accomplished through component properties.

Flux can be considered a variant of the observer pattern

A React component under the Flux architecture should not directly modify any props passed to it, but should be passed callback functions that create actions which are sent by the dispatcher to modify the store. The action is an object whose responsibility is to describe what has taken place: for example, an action describing one user 'following' another might contain a user id, a target user id, and the type USER_FOLLOWED_ANOTHER_USER[24]. The stores (which can be thought of as models) can alter themselves in response to actions received from the dispatcher.

This pattern is sometimes expressed as "properties flow down, actions flow up". Many implementations of Flux have been created since its inception, perhaps the most well-known being Redux which features a single store, often called a single source of truth.

<h2>React Native</h2>
React Native was announced by Facebook in 2015, applying the React architecture to native Android, iOS, and UWP applications.

<h2>History</h2>
In 2012 Mark Zuckerberg commented, "The biggest mistake we made as a company was betting too much on HTML5 as opposed to native". He promised that Facebook would soon deliver a better mobile experience.

Inside Facebook, Jordan Walke found a way to generate iOS UI elements from a background JavaScript thread. They decided to organize an internal hackathon to perfect this prototype in order to be able to build native apps with this technology.

After a few months of development, Facebook released the first version for the React.js Conf 2015. During a technical talk,Christopher Chedeau explained that Facebook was already using React Native in production for their Group App and their Ads Manager App.

<h2>Working principles</h2>
The working principles of React Native are basically the same as React except that it is not manipulating the DOM via the VirtualDom but some native views. It runs in a background process (which interprets the JavaScript written by the developers) directly on the end-device and communicates with the native platform via a serializable, asynchronous and batched Bridge

It can be seen that Facebook corrected the error that Mark Zuckerberg mentioned in 2012:[original research?] React Native doesn't rely on HTML5 at all, everything is written in JavaScript, and relies on native SDKs.

<h2>Hello World</h2>
A Hello, World program in React Native looks like this:

import React, { Component } from 'react';
import { AppRegistry, Text } from 'react-native';

export default class HelloWorldApp extends Component {
  render() {
    return (
      <Text>Hello world!</Text>
    );
  }
}

// Skip this line if using Create React Native App
AppRegistry.registerComponent('HelloWorld', () => HelloWorldApp);

// The ReactJS code can also be imported into another component with the following code:

import HelloWorldApp from './HelloWorldApp';
<h2>Future development</h2>
Project status can be tracked via the core team discussion forum. However, major changes to React go through the Future of React repository issues and pull requests.This enables the React community to provide feedback on new potential features, experimental APIs and JavaScript syntax improvements.

<h2>Sub projects</h2>
The status of the React sub-projects used to be available in the project wiki.

<h2>Facebook CLA</h2>
Facebook requires contributors to React to sign the Facebook CLA

<h2>Criticism</h2>
A criticism of React is that it has high memory (RAM) requirements, since it uses the concept of a "Virtual DOM". This is where "a representation of a UI is kept in memory and synced with the 'real' DOM by a library such as ReactDOM"


<h2>Refrence Site</h2>

https://www.wikipedia.org/

