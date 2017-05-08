---
layout: lesson
title: "Lifecycles"
permalink: /a6-lifecycles/
---

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
