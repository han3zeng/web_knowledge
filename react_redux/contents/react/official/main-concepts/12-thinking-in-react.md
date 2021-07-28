## How to define component
* based on the API data
* single responsibility principle
* match with mockup layer


## Steps
1. form component hierarchy
2. build static version
    * top-down: simple page
    * bottom-up: complex page
3. interactive version
    * state
        * DRY (Don't Repeat Yourself)
            * Figure out the absolute minimal representation of the state

4. define what you should put into state
    * Is it passed in from a parent via props? If so, it probably isn’t state.
    * Does it remain unchanged over time? If so, it probably isn’t state.
    * Can you compute it based on any other state or props in your component? If so, it isn’t state.

5.  Identify Where Your State Should Live
* Identify every component that renders something based on that state.
Find a common owner component (a single component above all the components that need the state in the hierarchy).
* Either the common owner or another component higher up in the hierarchy should own the state.
* If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

## refs
* https://reactjs.org/docs/thinking-in-react.html
