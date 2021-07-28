## What is Context
* solved problem: pass props to different components at the leaf of different sub-trees without passing props through intermediate components (prop-drilling)
* goal: share and pass the state to targeted component
    * it is not a state management api

* legacy context design flaw:
    * if the intermediate component is pure component or re-render depends on shouldUpdateComponent, the context will be blocked

## What is Redux
* manage centralize global state
* has predictable behavior
    * functional programming spirit
        * avoid side effects + immutable state
            * reducer
            * middleware (redux thunk) for async calls
* use context internally
    * avoid prop drilling


* why use it
    1. in early days, developers need to avoid props-drilling + legacy context design flaw
    2. Wanting to write your state management logic completely separate from the UI layer
    3. Sharing state management logic between different UI layers (such as an application that is being migrated from AngularJS to React)
    4. Using the power of Redux middleware to add additional logic when actions are dispatched
    5. Being able to persist portions of the Redux state
    6. Enabling bug reports that can be replayed by developers
    7. Faster debugging of logic and UI while in development

## State Management
* store an initial value
* read the current value
* update a value

## use case summary
* only need to avoid prop-drilling: context
* have some moderately complex react component state: context + userReducer
* has complex state management, has to track state history, manage side effects: redux  

## refs
* [Mark Dev's BLog](https://blog.isquaredsoftware.com/2021/01/context-redux-differences/#understanding-context-and-redux)
* [Dam Abramov](https://medium.com/@dan_abramov/you-might-not-need-redux-be46360cf367)
