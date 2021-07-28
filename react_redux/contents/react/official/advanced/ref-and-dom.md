# Refs and the DOM

## Overview
* typical data flow in react
    * unidirectional flow -> props (parent to children)

* alternative
    * refs
        1. instance of component
        2. DOM element

## When to use
* use it as last resort

## how to use [3 ways]
* createRef (class component) API
    * steps
        * this.Ref = React.createRef()
        * this.Ref.current
        * <div ref={this.Ref} />
    * life cycle
          * React will assign the current property with the DOM element when the component mounts, and assign it back to null when it unmounts. ref updates happen before componentDidMount or componentDidUpdate lifecycle methods.
* userRef (function component) API
* [callback ref](https://reactjs.org/docs/refs-and-the-dom.html#callback-refs) pattern
    * life cycle
        * React will call the ref callback with the DOM element when the component mounts, and call it with null when it unmounts. Refs are guaranteed to be up-to-date before componentDidMount or componentDidUpdate fires.

## Accessing Refs
* two types
    1. ref to DOM element
    2. ref to instance of class component
* function components can't be ref because they don't have instances
    * solutions
        1. [forward refs](https://reactjs.org/docs/forwarding-refs.html)
        2. forward refs + [useImperativeHandle](https://reactjs.org/docs/hooks-reference.html#useimperativehandle)


## Exposing DOM Refs to Parnet Components
* three solutions
    1. parent handler
        * pass a method to child to fetch ref (callback ref)
        * [use createRef](https://gist.github.com/gaearon/1a018a023347fe1c2476073330cc5509)
    2. ref forwarding

## Callback Refs caveats
* ref callback === inline function
    * during update
        * called twice
            1. null
            2. DOM element
* solution
    * ref callback === bound method


## findDOMNode
* use it as Escape Hatch
    * you should consider refs first
        * https://reactjs.org/docs/react-dom.html#finddomnode
        * https://reactjs.org/docs/strict-mode.html#warning-about-deprecated-finddomnode-usage

## Note
* class component: [createRef](https://reactjs.org/docs/refs-and-the-dom.html#adding-a-ref-to-a-class-component)
* function component: [useRef](https://reactjs.org/docs/refs-and-the-dom.html#refs-and-function-components)
