## Overview
* for check
* do not render UI
* run in dev mode only


## Check the following
* unsafe lifecycle
* deprecated findDOMNode
* string ref api
* legacy context api
* unexpected side effect



#### Side Effects
* react does work in two phases
    1. render
        * run reconciliation algorithm to find the differences between previous and current result (in react DOM tree)
        * life cycle
            * constructor
            * UNSAFE_componentWillMount
            * UNSAFE_componentWillReceiveProps
            * UNSAFE_componentWillUpdate
            * getDerivedStateFromProps
            * shouldComponentUpdate
            * render
            * setState (run the first argument)
    2. commit
        * update real DOM nodes
        * life cycle
            * componentDidMount
            * componentDidUpdate


* what are side effects
    * modifying variables outside of the instance, async operations, etc.
        * memory leaks || invalid application state
            * example:
                * say you modify store of state manager in constructor method and it has been instantiated multiple times, then you get the invalid states

* how to determine there are side effects
    * strict mode call following methods twice (only in dev mode)
        * Class component constructor, render, and shouldComponentUpdate methods
        * Class component static getDerivedStateFromProps method
        * Function component bodies
        * State updater functions (the first argument to setState)
        * Functions passed to useState, useMemo, or useReducer

* Starting with React 17, React automatically modifies the console methods like console.log() to silence the logs in the second call to lifecycle functions. However, it may cause undesired behavior in certain cases where a [workaround](https://github.com/facebook/react/issues/20090#issuecomment-715927125) can be used.
    * I don't fully understand this
