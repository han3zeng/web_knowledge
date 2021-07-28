# Reconciliation
* diffing algorithm



## Motivation
* state of the art algorithms O(n3) (give up such algorithm)
* the chosen algorithm
    * heuristic algorithm: O(n)
        1. Two elements of different types will produce different trees.
        2. The developer can hint at which child elements may be stable across different renders with a key prop.
* manipulate virtual DOM Tree (react elements === plain javascript object) is faster than manipulate real DOM Tree

## Diffing Algorithm
* Overview
    * render method
        * create a tree of react elements
        * compare old and new trees


* Different element types -> Different behavior


#### Elements of Different Types
1. tear down the old tree
    * componentWillUnmount
2. build the new one
    * UNSAFE_componentWillMount
    * componentDidMount


#### [DOM Elements of The Same Type](https://reactjs.org/docs/reconciliation.html#dom-elements-of-the-same-type)
* only update the attributes
* recurses on the chilrdren


#### Component Elements Of The Same Type
* cocmponent update
    * instance stays the same
    * state is maintained
    * steps
        1. React updates the props of the underlying component instance to match the new element
            * calls following methods on the underlying instances
                * UNSAFE_componentWillReceiveProps()
                * UNSAFE_componentWillUpdate()
                * componentDidUpdate()
        2. call render method
        3. initiate diff algorithm


#### Recursing On Children
* compare two subtrees (old and new)
* scenarios
    1. insert at head
    2. insert at tail
        * need keys

#### Keys
* The key only has to be unique among its siblings, not globally unique.
* problem of index as key
    * static order is fine
    * dynamic order may causes problems
        * two scenarios
            1. reorder
            2. delete uncontrolled inputs

## Refs
* https://reactjs.org/docs/reconciliation.html#dom-elements-of-the-same-type
