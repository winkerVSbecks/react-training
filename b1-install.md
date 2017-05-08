---
layout: lesson
title: "Installing Redux"
permalink: /b1-install/
---

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
