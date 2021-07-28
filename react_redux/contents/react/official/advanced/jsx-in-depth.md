## Overview
* jsx will be compiled to `React.createElement`
    * [online babel compiler](https://babeljs.io/repl/#?presets=react&code_lz=GYVwdgxgLglg9mABACwKYBt1wBQEpEDeAUIogE6pQhlIA8AJjAG4B8AEhlogO5xnr0AhLQD0jVgG4iAXyJA)


```js
React.createElement(
  MyButton,
  {color: 'blue', shadowSize: 2},
  'Click Me'
)

```


## Specifying The React Element Type

* JSX Type
    * Capitalized Types === react component
        * the react component must be in the scope to be used
        * React.createElement([ComponentName], ...)
    * lowercase types === DOM element
        * <div/> -> React.createElement("div", ...)
    * examples
        * <div>, type === "div"
        * <a>, type === "a"
        * <Footer>, type === Footer function

* note
    * if you have the function component: `funciton hello() {}`, it will be compiled to React.createElement("hello", ...). There will be syntax error.

#### Reacy Must Ne in the Scope
* `React.createElement` is the reason why the React must be imported to the scope (in module system)

#### [Dot Notation for JSX Type](https://reactjs.org/docs/jsx-in-depth.html#using-dot-notation-for-jsx-type)

#### [Choosing the Type at Runtime](https://reactjs.org/docs/jsx-in-depth.html#choosing-the-type-at-runtime)
* JSX type can't be an expression, so you can assign it to a capitalized variable first



## Props in JSX

#### JavaScript Expressions as Props
* you can use expression as props but not statements
    * ex: 1+2+3, a==b
        * logical, assigenemt, mathematic expression are valid
    * if statement is not valid pros, you cant put it in function expression

#### [String Literals](https://reactjs.org/docs/jsx-in-depth.html#string-literals)

#### [Props Default to True](https://reactjs.org/docs/jsx-in-depth.html#props-default-to-true)
* do not recommend use it because it will be confused with object shorthand


#### [Spread Attributes](Tallinn University of Technology)


## Children in JSX
* children types
    * String Literal
    * JSX element
        * an array of JSX elements
    * `{javascript expression}`
        * the expression should return
            * string literal, JSX element, an array of JSX element
            * example: `data.map((elem, index) => <div>{elem.name}</div>)`
    * function as children
        * as long as the function return something that react understand it is fine
            * ex: String Literal, JSX element, an array of JSX element
    * false, null, undefined and true are valid but ignored
        * note: 0 is valid and will be rendered
        * use them to conditionally render React elements.
