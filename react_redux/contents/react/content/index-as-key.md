## Problem
1. low re-render efficiency (sorting)
    * example
        * key=index=0, value = 6
        * key=index=1, value = 7
        * key=index=2, value = 3
        * key=index=3, value = 4
        * key=index=4, balue = 5
    * sort by value in ascending order, react will re-render all contents. However, if you use unique id react will know the subtree should be moved around and don't need to mutate it.
        * key=index=0, value = 3
        * key=index=1, value = 4
        * key=index=2, value = 5
        * key=index=3, value = 6
        * key=index=4, balue = 7

2. deletion problem
    * uncontroll inputs (state sotred in the real DOM)
        * store value in real DOM
        * examples
            * initial state
                * key=index=0, value=3
                * key=index=1, value=4
            * delete input with value=3
                * key=index=0, value=3 (still remain in the browser)
            * reason
                * react see the virtual DOM with key 0 still reamin intact, and the virtual DOM with key 1 got removed, so react should maintain the real DOM with key 0 which has value 3 and remove the DOM with the value 4

## refs
* https://medium.com/@vraa/why-using-an-index-as-key-in-react-is-probably-a-bad-idea-7543de68b17c
* https://stackoverflow.com/questions/46477711/react-error-when-removing-input-component
* https://stackoverflow.com/questions/46735483/error-do-not-use-array-index-in-keys
* https://codesandbox.io/s/vigorous-morning-6xexu?file=/src/App.js
