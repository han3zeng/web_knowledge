## e
* synthetic event
    * react create it
    * a wrapper around native event
    * normalized (cross browser)

## handling event in 3 types
* types
    1. arrow function
    2. bind in constructor
    3. class fields syntax

* notes
    * arrow function pass as props will cause performance issue
        * new funcion in each render -> new props -> re-render
        * solution: bind or class fields syntax
    * pass arguments in following waya are good at most of time
        ```
          <button onClick={(e) => this.deleteRow(id, e)}>Delete Row</button>
          <button onClick={this.deleteRow.bind(this, id)}>Delete Row</button>
        ```
        * These two methods may also cause perforemance issue
            * solution: using data-attributes

## Refs
* https://reactjs.org/docs/handling-events.html
* https://reactjs.org/docs/faq-functions.html
* [static field syntax](https://medium.com/@charpeni/arrow-functions-in-class-properties-might-not-be-as-great-as-we-think-3b3551c440b1)
