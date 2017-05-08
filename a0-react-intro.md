---
layout: lesson
title: "Introduction to React"
permalink: /a0-react-intro/
---

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
