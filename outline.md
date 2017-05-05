---
layout: lesson
title: "Outline"
permalink: /outline/
---

## Objectives

This training consists of:

-   Part 1: This is an introductory 3 hour course on React using the
    *create-react-app* tool. It is geared for Javascript developers who
    are interested in diving into the React library and have a good
    understanding of basic ES6 features. The structure of the course *will
    start with a few slides and dive into a full live coding *tutorial
    that the students can follow along.

-   Part 2: This is an introductory 2 hour course on Redux using an
    existing React application that was built in part 1 of this
    series. It is geared towards Javascript developers who have
    previous understanding of the React library, basic ES6 features,
    and would like to learn state management through Redux. We will
    transform an existing app to include redux in order to be
    extensible and scalable. By the end of the course the students
    will have a working react + redux application. The structure of
    the course will start with a few slides and dive into a full live
    coding tutorial that the students can follow along.

At the end of each part we will have a fully functioning application.
Along the way, students will learn current best practices for building
fast, scalable code. Each course builds on top of the previous course
and extends the web app. However, students can jump into whichever
module they prefer if they have experience already in the previous
ones.

## Prerequisits 

-   NPM and Node v6+ <http://nodejs.org/download/>
    -   The download above should install two commands: node and npm.
    -   npm may require some extra configuration to set permissions properly on
        your system.

-   A code editor.
    Any text editor will work.
    At Rangle.io, the most popular editors/IDEs are:
    -   [Vim](http://www.vim.org/download.php)
    -   [Sublime Text](http://www.sublimetext.com/)
    -   [Atom](https://atom.io/)
    -   [WebStorm](https://www.jetbrains.com/webstorm/)

-   Some understanding of JavaScript ES6:
    -   Classes
    -   Default Params
    -   Template Literals
    -   Destructuring
    -   Arrow Functions
    -   Promises
    -   let and const
    -   Modules

Visit [this link](https://rangle-io.gitbooks.io/react-training/content/book/es6_constructs/) for a refresher.

## Overview 

-   First session is about React only
    -   Leverage create-react-app to streamline setup
    -   State & Props
    -   Stateless/Stateful components
    -   JSX
    -   Lifecycle methods
    -   PropTypes
    -   DOM mounting
    -   REST API (fetch)
    -   createClass() vs class vs function
    -   Build a basic app starting from a dumb component

-   Second session introduces Redux
    -   Illustrate how redux solves the problem of global variables
        (i.e. sharing data between containers)
    -   Containers becoming redux aware (via connect)
    -   Action creators
    -   Reducers
    -   Constants for action names

-   Last session is for advanced topics using React and Redux
    -   Jest/Enzyme testing
    -   Immutable.js
    -   Selectors
    -   Sagas
    -   Scaling concerns
    -   Performance

## Part 1: React

-   Introduction
    -   What did we have before React? jQuery
        -   How we use to write code was like mixing ingredients sequentially
            -   Inconsistent; DOM could have been mutated by something else
            -   DOM changes were tedious; regression bugs
            -   Very slow development
            -   Crazy to scale
        -   Using React, is like using a bread machine
            -   Throw all ingredients in and see what comes out
            -   Reliable
            -   Consistent
    -   "I already know Angular, why do I need React?"
        -   You don't; Angular can do everything React can and more
        -   It may be overkill
        -   Learning curve
        -   You want the right tool for the job
            -   React is great for prototyping, small apps
            -   Angular is good for large, enterprise apps
            -   Angular is also MVC, which may be more than you want to or need
        -   Angular is to React as a Kitchen is to an Oven
        -   Size difference
        -   React does one thing really well; just the view
            -   Can be rendered on different systems/devices due to the rendering being decoupled from the device/system
        -   In order to really compare React with Angular, you should be talking about React+Redux.
            More on this during the second part of the training.

-   Thinking in Components
    -   Atomic Design Principle: Atom, Molecule, Organism
    -   Diagram of UI with boxes around Atoms, Molecules, Organisms
    -   Components allow us to encapsulate style, behavior, and markup into one neat little package and reuse these components everywhere.
    -   Components are like javascript functions.
        -   They accept arbitrary inputs (called props) and return React elements describing what should appear.

-   React Lingo
    -   Virtual Dom - React's local copy of the DOM which allows react to do computation/diffs on it way faster than browser specific dom.
    -   We use Props; explain what Props are.
        -   Just like pure functions, a react component must never modify its inputs (props)
        -   Ingredients as an analogy
        -   Given a certain set of props, the UI always looks this way. (pure function)
    -   State should be explained clearly as it is an abstract term that some people may have a hard time wrapping their minds around
        -   Analogy: it's like memory for your component
        -   Using analogy of a snapshot of the progression of the ingredients being mixed (steps); or like Time machine on mac
    -   We pass down state as props. Unidirectional data flow.
        -   This makes me think "How does data go back to the parent?"
        -   Answer is I can provide you with a function, as a prop, to notify the parent of something
    -   if a component has state, only that component can modify its own state.

### Live Coding - 2h 40min

See github repo for working code on each section. Each folder begins
where the previous one ended.
<https://github.com/aneagoie/react-training-RoboDex>

If you have issues running npm test on macOS Sierra, see here for
solutions:
<https://github.com/kst404/e8e-react-scripts/commit/c0666cfedc066532db712596fe01b47559ee4dda>

### Lesson 1

-   Go into a coding directory

-   Run command: **create-react-app Robodex**

-   Change to that directory and run **npm start**

-   Show the audience the browser that opened with the app running

-   Open a code editor in the src folder

-   TODO: set your code editor theme for high contrast and easy to read (large font)
    -   Might be a good idea to split screen with code editor and browser to
        show how hot reloading works

-   Show index.js code and explain the ReactDOM.render().

-   Use this opportunity to change App component to a hello world example (in a div).

### Lesson 2

Now we'll make a component from the markup

-   Create HelloComponent (stateless, function)
    -   Create a function called HelloComponent
    -   Write some JSX in the return statement (i.e. <h1>Hello World</h1>)
    -   Add the export default statement

-   Open the index.js file
    -   Replace the <App /> with <HelloCompoent /> and save
    -   You should see an error because the import is missing
    -   Once you add the import, you'll notice another error
    -   Add react import to hello component
    -   Talk about JSX

-   Update the render method to render HelloComponent

-   Demo

At this point we can use the hello world component to illustrate styling
using Tachyons.

-   Install tachyons via npm (i.e. npm install tachyons --save)

-   Add an import statement to index.js for tachyons (import ‘tachyons';)

-   Explain the class vs className (due to JS reserved words)

-   Apply a ‘f1' class to the div to show how the text font size increases, and ‘tc' class to center the text.

-   Introduce the idea of props and show a simple demonstration.

```
const Hello = (props) => {*
    return (
        <div className='f1 tc'>
            <div>Hello World</div>
            <div>Welcome to {props.company}</div>
        </div>
    );
};
```

### Lesson 3

We can now delete the HelloComponent and start building the app with the
Card component. We are going to make a Robodex.

-   TODO: show an image of the final screenshot, and/or demo

-   Create the Card.js as a stateless component

-   Return a static rendering of mock data

```
<div>
    <img alt='photo'
         src='[*//robohash.org/test*](https://robohash.org/test)?size=200x200'/>
    <div>
        <h2>Jane Doe</h2>
        <p>jane.doe@gmail.com</p>
    </div>
</div>
```

-   Add the Card component to index.js as an import and insert it into the render method

-   Then show what two of them would look like (div with two card components)
    -   Now would be a good time to convert the hard-coded values into props
        that are passed in

-   Now we're going to add json data to make each card different
    -   You can download robots.js from lesson 3's folder in the repo
    -   Or you can make your own array of objects with id, name, and email

-   `import { robots } from './robots';` in the index.js file.

-   Add a props for: id, name, email to component

```
function Card({ id, name, email }) {...}
```

-   Add propTypes (as required)

```
Card.propTypes = {
    id: React.PropTypes.number.isRequired,
    name: React.PropTypes.string.isRequired,
    email: React.PropTypes.string.isRequired
};
```

-   Update component render to use props, and add the below classes to the div.

```
<div className='bg-light-green dib br3 pa3 ma2 grow'>
    <img role='presentation'
         src={`//robohash.org/${id}?size=200x200`} />
    <div>
        <h2>{name}</h2>
        <p>{email}</p>
    </div>
</div>
```

-   Demo without changing index.js to illustrate the error you get when missing props

-   Update index.js to pass in props

-   Make sure each Card has different values to illustrate how each card is different but the same

-   Show how tedious it is to manually copy and past Card components in index.js:

```
<div>
    <Card id={robots[0].id} name={robots[0].name} email={robots[0].email} />
    <Card id={robots[1].id} name={robots[1].name} email={robots[1].email} />
    <Card id={robots[2].id} name={robots[2].name} email={robots[2].email} />
    <Card id={robots[3].id} name={robots[3].name} email={robots[3].email} />
</div>
```

## Lesson 4

OK, manually copy and pasting Card component doesn't work.
Create the CardList component

-   We'll create this using the markup in index.js as a hard-coded first step

-   Create an array of objects in the function that will hold the static data
    -   Then map over the array to generate the cards in the return JSX
    -   Make sure to demo the ‘key' is missing warning
    -   Then you'll see it's best to put it into a variable and inject the variable into the return JSX
    -   Then "wouldn't it be nice if we could pass this data into the component?"

-   Update the component to accept a prop: robots (which is our array of objects)

-   Add a prop type for robots as a required array

-   Update index.js to use the new component (add import statement, render)

-   Move the data to index.js and pass it into the CardList as robots

-   Passed in an array object into the CardList component

-   Demo

## Lesson 5

Creating the container

-   "As the app is now, it only renders once"
    -   We can illustrate this by placing a console log in one of the components

-   Demo using robot prop using setTimeout;
    -   Initialize it to empty array
    -   Set a timeout to change the array, but it won't update
    -   Creating a container will solve this, so let's move the code into App

-   Open the App.js file and take this opportunity to notice the ‘class' syntax and explain how it differs from the approach we've been using (function for dumb components)
    -   Comment out the class line and the render function declaration
    -   Add a function declaration called App (to make it look like a dumb component)
    -   Demo it to show it still works
    -   Show this as well:

```
var Greeting = React.createClass({
    render: function() {
        return <h1>Hello, {this.props.name}</h1>;
    }
});
```

-   Replace the content of App's render method with the render statement JSX

-   Now demonstrate changing state

```
constructor(props) {
    super(props)
    this.state = {
        robots: []
    }
    setTimeout(() => {
        this.setState({robots: apiRobots})
    }, 3000)
}
```

Next create the search/filter

-   Create a new component called SearchBox

-   In the return statement, just put an input, wrapped in a div:

```
<div className='pa2'>
    <input className='pa2'
           type='search'
           placeholder='search Robots...'
    />
</div>
```

-   Hookup communication between filter/search to contact list
    -   We want to use the text in the search box to filter our data
    -   Since the App component has the data,
        and it needs to send the filtered list to CardList,
        we need to have a way for the App component to know what was typed in the search box.
    -   We can provide searchbox a way of letting us know the text has changed.
    -   "How do we make the search box update the list?"
        -   Answer: "we use the parent as a common 3rd party"
    -   In order for us to create an event handler, we'll need to change the function to a class
    -   Now create a class method called onSearchChange that accepts an event
        (but does nothing yet; perhaps add a console.log(event.target.value) to prove the callback is working)
    -   Update the render to pass the onSearchChange to SearchBox
    -   Create a prop that will be called onSearchChange (so not confuse with onChange for input)
    -   Add the propTypes
    -   Bind the onSearchChange to the input's onChange
    -   Demo the console log of the typing in the input
    -   Since we have data in the global scope,
        we should take this opportunity to create a constructor and bind the data to the class (this.robotInfo = [...])
        -   This keeps the data encapsulated in the component
    -   Going back to the search callback, "What do we do with this text (search term) now?"
        -   This discussion should lead into using state to store the search term
        -   Add a line in the constructor to set the default state:
            `this.state = { searchTerm: '' };`
        -   Update the onSearchChange to fire a setState
        -   By changing the state, it will cause a redraw
            -   Demo by adding a console log to render to indicate it's being called
        -   Show them the error of setState not being defined
            -   The method signature looks just like a non-arrow function without the function keyword, which means it has its own ‘this'
            -   Fix this by binding ‘this' in the constructor:
                `this.onSearchChange = this.onSearchChange.bind(this);`
            -   Or we can explain how to use an arrow function
                `onSearchChange = (evt) => { ... }`

-   Demo again and look at the console logs firing for each render call

-   Now we can filter, using the render method, replace the console log with a filter on the robots and replace the robots with this new value

```
const { searchTerm, robots } = this.state;
const filteredRobots = robots.filter(robot =>
    robot.name.toLowerCase().includes(searchTerm.toLowerCase()));
```

NOTE: At this point you should be at 2hrs; this would be a good
point to break until Part 2, leaving lesson 6 as a precursor to redux

### Lesson 6

-   Introducing lifecycle methods

-   Tell the audience about lifecycle methods, how they work, when they're called, what they're names are, etc.
    -   componentWillMount / componentDidMount
    -   componentWillUnmount
    -   componentWillReceiveProps
    -   componentShouldUpdate
    -   Use this image:

<http://www.codevoila.com/uploads/images/201607/reactjs_component_lifecycle_functions.png>

-   All lifecycle methods have the proper ‘this' context set, unlike methods you create (non-arrow functions)

-   Create a componentDidMount that will call apiCall(), which will be a method to return the static robot data

-   To illustrate isPending, set a timeout for fetching the data

```
componentDidMount() {
    setTimeout(() => {
        fetch('https://jsonplaceholder.typicode.com/users')
        .then(response => response.json())
        .then(data => this.setState({robots: data}))
    }, 3000)
}
```

-   Add isPending to state

-   Wrap fetch in a setTimeout

-   Add code to render to show loading indicator when isPending

-   Update code to use REST API for data instead of hard-coded

-   This will also allow us to demonstrate lifecycle methods

-   We'll need to create a function to fetch this data
    -   Make it return the same static data first
    -   Then update it to return a promise and resolve it instantly
    -   Then change it to use fetch

```
componentDidMount() {
    apiCall('https://jsonplaceholder.typicode.com/users')
    .then(response =>
        this.setState({
            robots: response,
            isPending: false
        })
    )
}
```

At this point we should review what the App component is

-   Container

-   Root Component (is top most component)

-   Smart Component (has logic)

-   Stateful component (has state)

Add a scrollable component

-   First create a div in the App.js (which will be moved to a component later)

-   Add the styling for the div (height, overflow-y, border)

```
<div style={
    {
        height: '80vh',
        overflowY: 'scroll',
        border: '1px solid black'
    }
}>
    {props.children}
</div>
```

-   Children is good to use when the component should be agnostic to its content

-   Move the div into a component, add props.children

-   This will give the opportunity to introduce props.children

-   Demo

### Conclusion

Go back to the last slide.

-   "What is React?"
    -   At this point we should know it consists of: components, state, props and JSX. This is to show how simple React really is; and how it isn't that complicated.
    -   To build interactivity, we combine callbacks (methods) with props, and state
    -   It's best practice as apps get bigger, it solves a huge problem that massive projects have faced in the past. This is why people love react. React has these walls to guide you in this style of mentality. So when you build apps, you are using good practices.

-   Review the thinking in components
    -   Show the final result on a web browser and explain breaking down components
        -   Card is a self contained component
        -   There are many cards, therefore a list component will be needed
        -   Some form of a container will be needed
        -   Search component
        -   Header

This ends the React training. See if anybody has any questions or
comments about the course.

## Part 2: Redux - Presenter Notes

Before starting into this content, it is a good idea to review the app as it is, and cover the basics at a high level again to refresh the audience.

Why use Redux?

-   Good for managing large state. React afterall, is just a view layer.

-   Do one thing really great; React does views really well; Redux handles state really well

-   Redux can manage state without managing a view

-   When projects become large, they need to share state between containers; redux solves this by providing a global state

-   Redux provides a framework for managing global state

-   Useful for sharing data between containers

-   Predictable state management using the 3 principles

-   Encourages the use of Immutability to help prevent unexpected errors

-   Easy to debug state-related issues

-   Manage state when your app becomes too big for it to just use setState()

The 3 principles

-   Single source of truth

-   State is read only

-   Changes are made using pure functions

Flux

-   Diagram showing dispatcher, action, etc.

-   Facebook created it

-   Unidirectional data flow

What is Redux?

-   A creation by Dan Abramov

-   Like a model layer (the ‘M' in MVC)

-   Implementation of flux architecture

-   Larger, global version of this.state

Redux Lingo

-   Action

-   Dispatch

-   Reducer

-   Store

Folder structure

-   Containers

-   Components

-   Reducers

-   Actions

-   Constants

Live coding

-   Clone the robodex repo and start it running
    -   Git clone
        <https://github.com/aneagoie/react-training-RoboDex>
    -   Npm install
    -   Npm start

## Lesson 1: install redux

The main idea is that you describe how your state is updated over time
in response to action objects, and 90% of the code you write is just
plain JavaScript, with no use of Redux itself, its APIs, or any magic.
Let's go over the core concepts:

- Clone the robodex repo and start it running

-   git clone
    <https://github.com/aneagoie/react-training-RoboDex>

-   npm install

-   npm start

We need to connect Redux to react. Redux can be used with anything so
first we need to download it's binding:
npm install --save redux react-redux

-   Only the containers know of the redux store and will be communicating
    with them. The components won't know anything (dumb/presentation
    components).

## Lesson 2: create the action, actiontype constant, and reducer

-   Create src/actions.js file (touch src/actions.js)

-   Create src/constants.js file (touch src/constants.js)

-   Edit the actions.js file
    -   Add action creator for setSearchTerm (text => dispatch(...))

```
export const setSearchTerm = (term) =>
({ type: ‘SET_SEARCH_TERM': payload: term })
```

-   Use a hard-coded string at first for type, but then explain why it's better to use a constant

-   Edit the constants file to export a new constant for the action type

```
export const SET_SEARCH_TERM = ‘SET_SEARCH_TERM';
```

-   Go back to the actions file
    -   Import the constant
    -   Replace the hard-coded type with the constant

-   Create a src/reducers.js file (touch src/reducers.js)

-   Edit the reducers.js file
    -   Create an initial state object that cannot be mutated (i.e. use const)
    -   Import the action type from constants
    -   Create function for the reducer
        -   Default state to initial state
        -   Default action to empty object (to prevent undefined error when accessing action.type in switch)
        -   Create a switch statement
            -   with a case for the action type
            -   Default statement for returning state
            -   Object.assign({}, state, {searchTerm: action.payload})
                === pure functions. You always return a new state in a reducer.
            -   Explain that you could use an if instead of a switch
            -   Explain that this function must be pure and return a valid state each time

## Lesson 3: provide the store

-   Create store (index.js)
    -   Import reducer
    -   Import createStore from redux
    -   Combine reducers? Or maybe wait until there are more than 1 reducer
    -   Const store = createStore(rootReducer)
    -   Before we add the provider
        -   Update `<App store={store} />`
        -   Open App.js
            -   Inside componentDidMount() add a console log for this.props.store to show what it has
            -   Then show the store contents by console logging this.props.store.getState()
            -   Now remove the console statements
    -   Go back to the index.js
        -   Remove the store prop from App
        -   Wrap the App in a `<Provider store={ store }> ... </Provider>`

## Lesson 4: connect the app to redux

-   connect() is optimized in order to avoid store.subscribe() on the component.

-   Make App redux aware (App.js)
    -   Add an import for the actions
    -   Add mapStateToProps(state) - What part of the store the container cares about.
        -   Hookup searchTerm from store
    -   Add mapDispatchToProps(dispatch) In addition to reading the state, container components can dispatch actions. In a similar fashion, you can define a function called mapDispatchToProps() that receives the [dispatch()](http://redux.js.org/docs/api/Store.html#dispatch) method
        -   Hookup the setSearchTerm action to accept an event object and pass into the action e.target.value
    -   Add connect() to default export
    -   It might be worth mentioning the mergeProps param of connect
    -   Remove the searchTerm from state
    -   Inside render()
        -   remove the searchterm from this.state
        -   add searchterm from props
        -   Remove the onSearchChange()
        -   Replace the render reference to this.props.onSearchChange
    -   Since we're now using Props instead State, update propTypes

## Lesson 5: Redux Logger

Now that we have a redux application running; how do we know what is
firing? What data is being passed? How would we debug any errors in
redux? The redux logger!

-   Install the logger via npm install redux-logger --save

-   Open the index.js file and add:

```
import createLogger from ‘redux-logger';
```

-   Create an instance of the logger by calling createLogger():

```
const logger = createLogger();
```

-   Ensure the applyMiddleware function is imported from redux

-   Update the createStore call to add a second argument:
    -   applyMiddleware(logger)
    -   So that it looks like:

```
const store = createStore(rootReducer, applyMiddleware(logger))
```

-   Now load the app and show the logs in the console

## Lesson 6: Redux Thunk

-   Run and discuss; walk through the code to review all the steps

-   Now let's do it again, this time with robot data being fetched from json

-   Start off by installing thunk and explaining what it provides
    -   npm install --save redux-thunk
    -   It's middleware that provides getState and dispatch to functions that are passed to dispatch; useful for side effects, like ajax calls
-   We're going to create a new action for fetching the robot data asynchronously
    -   Open the constants.js file
        -   add a new action types for pending, success, and error
    -   Open the actions.js file
        -   Import the constants you just created
        -   Add an action creator for fetching robot data
            -   Returns a function that accepts dispatch (and optionally getState since thunk provides it)
                -   Inside the function…
                -   Dispatch pending
                -   Call fetch
                -   On then fire the success action with payload
                -   On error fire the error action
    -   Open the reducers.js file
        -   Import the constants for the new action
        -   Create a new reducer for robots data
            -   Create a new initial state for robot data, is pending, and has error
            -   Create a reducer function that will implement the new constants
        -   Change the export default to export and add an export for the new reducer

-   Open index.js
    -   change the import statement for the reducer to use curly braces to import each of the reducers separately
    -   It might be a good idea to explain why using multiple files is better than multiple reducers in one file
    -   Illustrate combineReducers before calling createStore
        -   Add the import for combineReducers from redux
        -   Const rootReducer = combineReducers({ reducer1, reducer2 })
        -   Update createStore to use rootReducer
        -   Explain that this can be done as a default export too (in reducers.js)
    -   Import applyMiddleware from redux
    -   Import reduxThunk from redux-thunk
    -   Update createStore to pass a second param: applyMiddleware(reduxThunk)

-   Open App.js and import the new action

-   Update mapStateToProps and mapDispatchToProps
    -   Note, now that we're using combineReducers, you'll need to update the state.searchTerm to include reducer name (i.e. state.robotSearch.searchTerm)

-   Update propTypes

-   Remove the constructor

-   Replace the contents of componentDidMount to call the action to fetch robots

*Optional*

Update the code to show how you can do the same without thunk

-   Update the requestRobots action in actions.js

```
const requestRobots = (dispatch) => { dispatch (pending), fetch.then(dispatch(success)).catch(dispatch(error))
```

-   Open index.js and remove applyMiddleware and reduxThunk

-   Open app.js and change mapDispatchToProps()
    -   requestRobots: () => requestRobots(dispatch)

TODO if there is enough time

-   Implement another container to illustrate another redux aware component

-   Pass data between the containers

-   Split reducers into individual files into reducers folder

-   How to know when to create additional containers

-   Components are only for presentation; not for data proxy, thus redux instead of a container for just holding state

## Lesson 7: mergeProps

-   We're going to leverage mergeProps to help us with filtering robots

-   Open App.js and create a new function called mergeProps() that will take in two params, one for state props and one for dispatch props

-   Return all the state props and dispatch props along with a new one for filteredRobots that will apply searchTerm to robots data

-   Update the connect to pass mergeProps as the third param

-   Now update the render method to remove robots from props destructuring and add filteredRobots instead. Now you can remove the following lines for calculating filteredRobots

## React+Redux Advanced Topics

-   Isomorphic/Universal
    -   What is it (Server-side react rendering)
    -   How it works (node instance)
    -   Benefits (SEO, Caching)
    -   Examples (Priceline hotels without prices)
    -   renderToString()

-   process.env.NODE_ENV for build/dev
    -   Good for applying dev specific middleware
    -   Mocking out data when in dev mode

-   Routing
    -   React-router vs redux-router
        -   Use react-router until you have a need for redux-router
    -   Props provided (router, location, routeParams)
    -   <Route> and <Router>

-   Unit testing (Jest)
    -   https://facebook.github.io/jest/docs/tutorial-react.html
    -   https://facebook.github.io/jest/docs/getting-started.html
    -   Explain libraries included (mocha, chai)
    -   Show example of TDD
    -   coverage

-   Styling
    -   CSS processors provided
    -   Global vs component css
    -   Autoprefixer
    -   Using className and style?
    -   Mention libraries like Radium

-   A11y
    -   What is A11y?
        -   It's short for Accessibility (starts with ‘A', then 11 chars, and ends with ‘y)
    -   React Intl:
        <https://www.npmjs.com/package/react-intl>
    -   What do you need? Translations? Locale time/money?
    -   What packages exist

-   Analytics (redux-gtm)
    -   Redux GTM:
        <https://www.npmjs.com/package/redux-gtm>
    -   React Tag Manager:
        <https://www.npmjs.com/package/redux-gtm>
    -   The package created by rangle for analytics (thomas, ken ono)
    -   Implementing google tag manager?

-   Spread operator used for passing props

-   GraphQL
    -   <http://graphql.org/learn/>
    -   Need to keep the content lean as we'll have a GraphQL workshop
    -   -   It's an open source architecture, made by facebook
    -   Client/server architecture
    -   One endpoint for all queries
    -   Server is language agnostic
    -   Needs a server and client
    -   Client can be relay or apollo
    -   Uses a typing system
    -   Introspection via __schema and __types
    -   Useful for when you don't have the ability to change the back-end
    -   Query vs Mutation (GET vs POST)
    -   @include and @skip directives
    -   Can cache using data-loader to save requests (ideal for mobile)
    -   Builds a middle layer of data, thin but meaningful through schemas
    -   Thinking in graphs, not views or endpoints
    -   Client: apollo vs relay
    -   Asynchronous; a field resolve() can return a promise
    -   Limit queries for security (use timeout, or query depth) to prevent a DDOS via a circular reference
    -   Fragments help copy/paste of templates
    -   Naming is important, as you should be backwards compatible
        -   Use object references instead of copying data into new custom fields (ie. include a Person ref, having smallThumbnail, instead of a custom field like smallPersonThumbnail)
    -   Useful for decoupling your data from the source

-   Performance
    -   Reselect
    -   Immutablejs - <https://auth0.com/blog/intro-to-immutable-js/>
    -   PureComponent vs Component - (https://facebook.github.io/react/docs/react-api.html#react.purecomponent>
    -   shouldComponentUpdate() - <https://facebook.github.io/react/docs/optimizing-performance.html>
    -   perfTools - <https://facebook.github.io/react/docs/perf.html>

-   Observables

-   Children
    -   React.Children(), map, forEach, count
    -   <https://facebook.github.io/react/docs/react-api.html#react.children>

-   Context
    -   How do use it
    -   Why you shouldn't use it

-   Middleware (promiseMiddleware, devTools)
    -   List some useful packages

-   PropTypes
    -   shape()
    -   Exporting your proptypes to import for parents

-   Redux
    -   mergeProps (as third param for connect)
    -   localStorage for persisting state
    -   Observables
    -   Reducers per field vs per container (rangle vs josep)
    -   Pass object instead of mapDispatchToProps to second param of connect
        -   Dan talks about this in his egghead videos
        -   It will wrap dispatch around each function in the values, functional composition

-   Scalability

-   Might not need Redux (in small apps)

-   It might be a good idea to use fewest smart/stateful components when early in development or a very small app

-   As an app grows in size, you'll probably want to build out more containers, smart components, to spread out the logic and data

-   Start off with reducers.js then when you need more than one reducer
    -   create a reducers folder
    -   create index.js
    -   move the reducers.js into reducers folder and rename the file
    -   Add an import statement to index.js and export default combineReducers
    -   Then for all other reducers, add a reducer js file and import statement and update combineReducers()

-   Reselect library

-   Selectors can compute derived data, allowing Redux to store the minimal possible state.

-   Selectors are composable. They can be used as input to other selectors.

-   Reselect Selectors are efficient. A selector is not recomputed unless one of its arguments change.

### Presentation Ideas

-   Let the audience pick the high level topics and perhaps you don't need to cover some
    -   You can give a brief overview of the topics and let the audience pick what they want

-   Simple demo

-   Trivia/Crossword puzzle, statements with a blank that they can fill in the blank

-   Intelligent Interrupts
    -   Structure into your talk, breaks for the audience to interact
    -   Encourage a conversation about the topic
    -   Permission to interact
    -   Two sticky notes; one for passive help and one for active help

-   Balanced chance to speak, sticky note to indicate if you've spoken already to prevent over contributor

-   Bring paper, pens, and encourage doodling

-   Quiz them
    -   Mind maps; draw them while listening and compare at intervals
        -   Compare mind map at the end to my mind map; this encourages people to pay attention

-   Build something that represents the thing you were talking about
    -   I.e. building blocks to represent a pipeline of processes
