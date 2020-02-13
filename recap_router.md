## REACT ROUTER


With routes you can easily manage to render different React components dynamically in an application. Even in a single page application you need to keep an order (bookmarks, previous-next buttons).

A basic navigation example would be:

* Home --> Goes to the '/' path, the main page
* Users --> Shows you the specific users
* Contact

## How to (Steps):

In the terminal:
1. npm install react-router-dom

In index.js:
```javascript
import {BrowserRouter} from 'react-router-dom';
```

(at the end of the page:)
```javascript 
ReactDOM.render(<BrowserRouter><App /></BrowserRouter>, document.getElementById('root'));
```

In App.js:

Import Switch and Route:

```javascript
import {Switch, Route} from "react-router-dom";
```

Declare all the routes in the render of the component:

```javascript
<Switch>
    <Route path="/about">
        <About />
    </Route>
    <Route path="/users">
        <Users />
    </Route>
    <Route path="/">
        <Home />
    </Route>
</Switch>
```

(also can write it like this :)

<Switch>
    <Route path="/about" component={About}/>
    <Route path="/users" component={Users}/>
    <Route path="/" component={Home}/>
</Switch>
````

In Header.js (or whatever component you want, actually):

```javascript
import {Link} from 'react-router-dom';
```

In the same component (inside renter and <Router>):

<div>
    <ul>
        <li>
            <Link to="/">Home</Link>
        </li>
        <li>
            <Link to="/Users">Users</Link>
        </li>
        <li>
            <Link to="/Contact">Contact</Link>
        </li>
    </ul>
</div>

You can also change <Link> for <NavLink> if you want to add classes on it.


