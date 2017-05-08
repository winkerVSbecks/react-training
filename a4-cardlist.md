---
layout: lesson
title: "Creating a Card List"
permalink: /a4-cardlist/
---

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
