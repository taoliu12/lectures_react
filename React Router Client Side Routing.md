
# React Router

* Understand why routing is important and how it is different in React Router
* We'll set up React Router in a React App
* Go over `BrowserRouter`, `Link`, `Route`, and `Switch`.

## Resources

* [Example Video](https://www.youtube.com/watch?v=lps-Eq2QWxk)
* [React Router Quickstart](https://reacttraining.com/react-router/web/guides/quick-start)
* [Learn's Intro to Client-Side Routing](https://github.com/learn-co-curriculum/react-introduction-to-react-router)
* [A Simple React Router v4 Tutorial](https://medium.com/@pshrmn/a-simple-react-router-v4-tutorial-7f23ff27adf)

##### Client-side routing

None of our routes require a new `GET` request to the backend to get that page's HTML. 

##### Why do we even need routes?

* We can make urls that describe the action that the user might be taking

##### What are the drawbacks to client-side routing?

* We're loading all of our frontend at once, so it might add to the initial load time 

### Setup and Components

You can use `create-react-app` in conjunction with `react-router`, just install with `npm install react-router-dom`.

Now, we can add the requisite components with

```js
import { BrowserRouter as Router, Route, Link, Switch } from 'react-router-dom';
```

## Here are the Router components we use:

#### Router

We'll use this in one place in our application (and one place only). Very top level, essentially listening for when the route changes, and making that info accessible.

#### Route

Conditionally render a certain component based on what the route looks like.

#### Link

Changes the url we see in the browser, must have a 'to' prop.

#### Switch

Pick one of the following routes (the first that matches), don't look at the others (like an if/ else if/ else if). It is similar to what 'exact path' does.

#### Redirect

Forces a redirect to a particular route. We won't use this here.

### Using the Router Components

Go through the process of building a app with routing. Start by wrapping your top-level app in the router in `index.js`:

```jsx
<BrowserRouter>
  <App />
</BrowserRouter>
```

Now you can make your app render different components using `<Render />` At this stage, it helps to have a separation of information and navigation, so the links can live on their own.

##### Basic Routing
```jsx
<Switch>
  <Route path="/login" component={Login} />
  <Route path="/paintings" component={PaintingsContainer} />
  <Route path="/" component={About} />
</Switch>
```
##### Links

 Links (or NavLinks, which add styling functionality) go towards specific paths.
    <NavLink> is a special version of the <Link> that will add styling attributes to the rendered element when it matches the current URL.

```jsx
<Link to="/paintings" className="item">
  Paintings
</Link>
```
