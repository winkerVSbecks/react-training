---
layout: lesson
title: "Overview"
permalink: /overview/
---

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

## Lesson Plan

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
