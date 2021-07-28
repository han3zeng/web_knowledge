# Optimizing Performance

## Bundler, Task Processor
* [webpack with terser-webpack-plugin](https://reactjs.org/docs/optimizing-performance.html#webpack)


## Checking Tool
* react Profiler
* performance tab in chrome inspect

## Virtualize Long Lists

## Avoid Reconciliation
* Reconciliation Overview
    * compare current and new virtual DOM Tree to find the difference
    * update real DOM
* Methods
    * [s]houldComponentUpdate](https://reactjs.org/docs/optimizing-performance.html#shouldcomponentupdate-in-action)
        * Scenarios
            * shouldComponentUpdate === true
                * render same
                    * no need to update Real DOM
                * render different
                    * update real DOM
            *  shouldComponentUpdate === false
                * no need to re-render and recurse to sub trees

    * PureComponent
        * a **shallow comparison** of current and previous props and state.



## Caveats
* PureComponent problems
    * can't handle mutating data because of shallow comparison
    * solutions
        1. concat array
        2. [...old_array, 'new value']
        3. object.assign
        4. {...old_obj, newProp: 'newValue'}

## Process
* https://reactjs.org/docs/optimizing-performance.html#avoid-reconciliation
