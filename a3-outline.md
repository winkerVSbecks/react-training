---
layout: lesson
title: "Outline of Future Work"
permalink: /a3-outline/
---

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
