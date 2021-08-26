# Portals
* what for
    * render children into a DOM node that exists outside the DOM hierarchy of the parent component.

* syntax
```js
ReactDOM.createPortal(child, container)
```

* chiled: string, fragment, jsx element,


## Usage
* typical use case
    * modal
    * tooltips
    * hovercards
* common css features
    * z-index
    * overflow: hidden
* notes
    * manage focus
    * follow [WAI-ARIA Modal Authoring Practices](https://www.w3.org/TR/wai-aria-practices-1.1/#dialog_modal)

## [Event Bubbling Through Portals](https://reactjs.org/docs/portals.html#event-bubbling-through-portals)
* propagation bubble through portal as if it exist in the react DOM tree hierarchy
* context works as if it exist in the react DOM tree hierarchy

## References
* [Portals](https://reactjs.org/docs/portals.html)
