## Overview
* HOC it is a pattern
* takes a wrappedComponent and return a brand new component

## Rules
* HOC is pure function
    * node side effects
    * do not modify wrapped component
    * pass through all props
    * add new props
* HOC is a container
    * the container offer common functions
* basic usage
    * HOC (container) fetch data
    * wrapped component use data


## Implementation Notes
* pass all unrelated props (at HOC's point of views) to newly created component
    * maintain similar interface for the wrappedComponent
* pass specific props
    * add specific feature to wrappedComponent
* hoist static method


## Composition over Mutating original component
* Mutation Problem
    * if the wrapped component wrapped by multiple container(HOC), the method may be overridden multiple times
* [example](https://reactjs.org/docs/higher-order-components.html#dont-mutate-the-original-component-use-composition)

## HOC === Parameterized Container components
* Container components
    * Separates high and low level concerns
        * example:
            * container
                * subscription and state
                * pass datra as props

            * components:
                * receives props and renders UI

*  HOCs use containers as part of their implementation. You can think of HOCs as parameterized container component definitions.

## [Convention: Maximizing Composability](https://reactjs.org/docs/higher-order-components.html#convention-maximizing-composability)
* the HOC can accept multiple parameters to
    * specify a component’s data dependencies
    * to implement any specific feature

* connect(...args)(wrappedComponent)
    * connect is a higher order function which returns a higher-order component

* work with withRouter and connect
    * use compose
    * check the example

* compose utility function third-party libraries
    * lodash.flowRight, Redux, Ramda


## Name Convention
* for dev tools
* `with[FnName].displayName = with[FnName]([nameOfWrappedComponent])`

## Caveats
1. Don't create HOC in render method
    * mount unmount every render
        * lose state
        * low performance (reconciliation algorithm)

2. static methods
    * hoist
        * copy all non react static methods from wrappedComponent to HOC
        * tools: [hoist-non-react-statics](https://github.com/mridgway/hoist-non-react-statics)
    * export the function which will be used as static method

3. Refs aren't passed through
* ref is not a real prop, so you can not pass it from HOC to wrapped component (top down)
    * bottom up solution
        1. forward refs
        2. callback refs


## Examples
* redux: connect
* Relay: createFragmentContainer
