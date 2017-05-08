---
layout: lesson
title: "Providing a Store"
permalink: /b3-store/
---

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
