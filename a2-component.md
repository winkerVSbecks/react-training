---
layout: lesson
title: "Making a Component"
permalink: /a2-component/
---

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
