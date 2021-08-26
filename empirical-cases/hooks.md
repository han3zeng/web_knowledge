## React Hook with debounce onChange (form)
* you can't debounce a function, because each state change you create a new function
    * solutions
        1. debounce event callback
        2. create a new debounce hook


## React hook v.s Render Props
* hook (mix-in)
    * pros and cons
        * pros
            * avoid pyramid hell
        * cons
            * rerender parent component
* render props
    * pros
        * contain whole logic and re-render process in single component
    * cons
        *  pyramid hell
* [refs](https://javascript.plainenglish.io/render-props-vs-hooks-a73ec72180ed)

## useState v.s useReducer
* useReducer
    * when to use it
        * complex state management
        * want to test easily
* [ref](https://dev.to/spukas/3-reasons-to-usereducer-over-usestate-43ad)
