## Overview
* create an reusable component
*  sharing code between React components using a prop whose value is a function.
*  a render prop is a function prop that a component uses to know what to render.
* you can implement most higher-order components (HOC) using a regular component with a render prop.
* solve cross-cutting concern


## Reuse Code
* mixin -> HOC -> Render Props
* same goals
    * code reuse but no inheritance


##### Mixin
* goals:
    * instead of inheriting whole class, we just copy the behavior (functions, methods)
* Problems
    * can't work with class
    * naming collisions
        * multiple mixins
    * implicit state
    * static composition
* solution
    * HOC

##### HOC
    * problems
        * static composition
            * compose during the class is created
        * need a lot boilerplage code
            * create a new class rather than insert mehotds to existing component
                * need to pass props to wrapped compoennt
                * hoist static props from weapped component to wrapper
    * solution
        * render props


##### Render Props
* benefit
    * dynamic composition
        * compose in render, takes advantage of the full react lifecycle
    * clear state source
    * no nameing colissions
    * class syntax support
    * no boilerplate code
    * good for typescript
* caveats
    * if want to use it with pure component, you have to pass the prop with instance method

## Implementation Example
* react router

## Refs
* [render-props](https://reactjs.org/docs/render-props.html)
* [mixin](https://javascript.info/mixins)
* [why render props - Michael Jackson](https://medium.com/componentdidblog/use-a-render-prop-50de598f11ce)
* [mixin problem - Don Abramov](https://reactjs.org/blog/2016/07/13/mixins-considered-harmful.html)
