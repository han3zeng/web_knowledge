* JSX produces React “elements”

* ReactDOM
    * render
    * modify DOM elemnt to match React element

* const element = (<h1>test</h1>)
    * `(<h1>test</h1>)` === jsx syntax
        * babel transfer it to `React.createElement(...)`
            * return an object which is a react element

* react element is a plain object which is is cheap to create (compare to real DOM element)

* `ReactDOM.render(element, document.getElementById('root'));`
    * everything in root div will be managed by React DOM

* react element is immutable

* React DOM only update the content that has been changed even though each time we give an immutable new element to reactDOM to render


## refs
* [Rendering Element](https://reactjs.org/docs/rendering-elements.html)
