# Context


## When to Use Context
* prevent prop drills
* share global data over the tree
* cases
    * locale
    * UI Theme
    * preference
    * authenticated status
    * data cache


## Choose composition over context
* reasons
    * context make components hard to be reused
    * composition is simpler solution

* Composition
    * instead of passing down props, you can pass down the whole component with those needed props
    * benefit
        * flexible, reusable lower level component
    * downside
        * complex top level component

## API
* React.createContext
    * `myContext = React.createContext(defaultValue)`
* Context.Provider
    * `<myContext.Provider value={} />`
          * value is undefined || none -> get the defaultValue
* Class.contextType
    * consuming component set the static property (contextType === myContext)
* Context.Consumers
    * for funciton component
* Context.displayName
    * `myContext.displayName = 'xxx' `
    * for react DevTools


## [Examples](https://reactjs.org/docs/context.html#examples)
* dynamic
* toggle in child component
* multiple contexts

## Caveats
* pass plain object as vlue for `<myContext.Provider value={} />`
      * if the component of providewr rerender, all its consumers are re-rendered no matter what
          * solutoin: set object in state of component then pass the object as this.state.object


## Refs
* [react official web](https://reactjs.org/docs/context.html)
