## React LifeCycles

React is divided into 4 parts
- Pre-Mounting
- Mounting
- Updating
- UnMounting

### What should I know
- *constructor(props)*
- *render()*
- *componentDidMount()*
- *componentDidUpdate()*
- *componentWillUnmount()*

### Birth (Pre-Mounting Phase & Mounting Phase)
- *constructor(props)*
  - since react is still javascript, constructor will still run during the initialization of the component
  - called before it is mounted
- *render()*
  - initial render
    - returns JSX in order for React to inject into the DOM
- *componentDidMount()*
  - invoked immediately after a component is mounted (inserted into the tree). Initialization that requires DOM nodes should go here. If you need to load data from a remote endpoint, this is a good place to instantiate the network request.

### Life (Updating Phase)
- *render()*
    - Re-renders with the new information
- *componentDidUpdate(prevProps, prevState)*
    - used for things like focusing on a specific form input or doing the effect of scrolling down a window
  - invoked immediately after updating occurs. This method is not called for the initial render
  
  - watch out for infinite loops if setting state!

### Death (Unmounting Phase)
- *componentWillUnmount()*
  -  invoked immediately before a component is unmounted and destroyed. Perform any necessary cleanup in this method, such as invalidating timers, canceling network requests, or cleaning up any subscriptions that were created in componentDidMount().
   - This is the only lifecycle event in the unmounting stage, this is used to clean up any events, animations, intervals, etc...




### Links
    https://learn.co/tracks/online-software-engineering-structured/react/lifecycle-methods/react-component-lifecycle-overview

    https://reactjs.org/docs/react-component.html

    [Lab] https://github.com/taoliu12/react-component-mounting-lab-v-000

    [Docs](https://reactjs.org/docs/react-component.html#the-component-lifecycle)

    [React Lifecycle Methods Diagram](http://projects.wojtekmaj.pl/react-lifecycle-methods-diagram/)








       constructor -> render -> componentDidMount 
    if this.setState is called, it triggers: render -> componentDidUpdate ...
    if this.setState is called, it triggers: render -> componentDidUpdate ...
    ...
    ...
    