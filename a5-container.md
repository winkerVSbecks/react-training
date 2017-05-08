---
layout: lesson
title: "Creating the Container"
permalink: /a5-container/
---

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
