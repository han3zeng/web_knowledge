## Error Boundaries
* goal: prevent javascript error from breaking whole react app.

## Overview
* features
    * catch Javascript error in child component tree
    * log those errors
    * provides fallback UI
* when to catch
    * rendering
    * life cycle
    * constructors


## Do not catch errors for
* event handlers
* async code
    * setTimeout
    * requestAnimationFrame
* SSR
* Errors that thrown in error boundary component itself


## [Implementation](https://reactjs.org/docs/error-boundaries.html#introducing-error-boundaries)
* only class component can be error boundary component
* use either or both of the following lifecycle method
    1. getDerivedStateFromError
        * for fall back UI (state change)
    2. componentDidCatch
        * for logs
* declare an Error componany and use it all over the app


## Where to place Boundary Component
* note
    * boundary component is just like catch in javascript. The error will propagate from bottom to top.
* up to developer
    * place boundary at route level or component level. If the component level do no handle the error, the route error boundary component may catch the error.

## New Behavior for Uncaught Errors
* < 16: leave the error ui
* >= 16: unmount whole react component tree

## Error Checking for React
1. error boundary component
2.  JS error reporting services
    * Example: Sentry, Bugsnag, Raven.js, etc.


## Component Stack Traces
* Need to add the plugin to babel configuration
      * [add babel plugin-transform-react-jsx-source](https://www.npmjs.com/package/@babel/plugin-transform-react-jsx-source)

* Component names displayed in the stack traces
    * component.displayName || Function.name

* in older browser you may need polyfill for function.name to work
    * [ref](https://github.com/JamesMGreene/Function.name)

## try/catch v.s Error Boundary Component
* try/catch for imperative code
* Error Boundary for declarative code
    * catches error occurs in componentDidMount, setState, etc.

## [Event Handler](https://reactjs.org/docs/error-boundaries.html#how-about-event-handlers)
* use try/catch

## refs
* [react official](https://reactjs.org/docs/error-boundaries.html)
