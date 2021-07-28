## Ovweview
* why we need ref forwarding
    * expose child ref to parent component

* example
```js
  const FancyButton = React.forwardRef((props, ref) => (
  <button ref={ref} className="FancyButton">
    {props.children}
  </button>
  ));

  // You can now get a ref directly to the DOM button:
  const ref = React.createRef();
  <FancyButton ref={ref}>Click me!</FancyButton>;
```


## For maintainers
* when you use forwardRef, you should treat it as breaking changes

## [Useful for HOC](https://reactjs.org/docs/forwarding-refs.html#forwarding-refs-in-higher-order-components)
* you will refer to HOC rather than the wrappedComponent without special treatment
* forward ref example
```js
    function logProps(Component) {
      class LogProps extends React.Component {
        componentDidUpdate(prevProps) {
          console.log('old props:', prevProps);
          console.log('new props:', this.props);
        }

        render() {
          const {forwardedRef, ...rest} = this.props;

          // Assign the custom prop "forwardedRef" as a ref
          return <Component ref={forwardedRef} {...rest} />;
        }
      }

      // Note the second param "ref" provided by React.forwardRef.
      // We can pass it along to LogProps as a regular prop, e.g. "forwardedRef"
      // And it can then be attached to the Component.
      return React.forwardRef((props, ref) => {
        return <LogProps {...props} forwardedRef={ref} />;
      });
    }
```

## [Naming for Dev Tools](https://reactjs.org/docs/forwarding-refs.html#displaying-a-custom-name-in-devtools)
