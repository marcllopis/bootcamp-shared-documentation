# Catch
  is a mthod how deals with errors and return a friendly message instead of a native error.

```
  import axios from 'axios';

  function handleError(error) {
    return error.toString()
  }
  class App extends Component {
    state = {
      info: {},
      error: ''
    }
```
#### with FETCH
        componentDidMount() {
       fetch('https://api.github.com/users/marclloasdasdpis')
         .then((response) => {

You need to "force" an error on the fetch sinceany status code
is rendered as ok. If the response is not ok, we throw an error.

```
    if (!response.ok) {
       throw new Error(`There was a problem with your request. Error code: ${response.status}, ${response.statusText}`);
     }
     return response.json();
   })
   .then(data => this.setState({info:data}))
   .catch((error) => {
     let errorString = `Your fetch request didn't work, it returned the following: ${error.toString()}`
     this.setState({
       error: errorString
     });
   });
   }
 ```
### with AXIOS

```

  async componentDidMount() {
     1st way with Try and Catch
       try {
         const {data} = await axios('https://api.github.com/users/marcasdallopis')
         this.setState({info: data})
       }
      catch(error) {
         let errorString = `Your fetch request didn't work, it returned the following: ${error.toString()}`
         this.setState({
           error: errorString
         });
       }
```

 2n way just with a .catch after axios call

```
      const data = await
        axios('https://api.github.com/users/marsdsdcllopis').catch(error =>
          this.setState({
            error: handleError(error)
          })
        )
      if (data) {
        this.setState({
          info: data.data
        })
      }
    }
    render() {
      return (
        <div>
          <h1>Hello</h1>
          {
            this.state.error
              ? this.state.error
              : this.state.info.name
          }
        </div >
      );
    }
  }
  export default App;

  ```

  # React Components Lifecycle

  There are 3 phases:

  1. Mounting (creating):

  The first part is the constructor, and it's mandotiry to use it. After we have the functions and then a render() method and it's the part who contains HTML.

  componentDidMount():

  This method is available after the component has mounted. That is after the HTML from render has finished loading. It is called once in the component life cycle and it signals that the component and all its sub-components have rendered properly.

  This is the best place to make API calls since, at this point, the component has been mounted and is available to the DOM. Generally, componentDidMount is a good place to do all the setup you couldn’t have done without the DOM. So here is a bunch of things you can do with this method:
  Connect a React app to external applications, such as web APIs or JavaScript frameworks.
  Set Timers using using setTimeout or setInterval.
  Add event listeners.
  Draw on an element you just rendered.


```
  componentDidMount() {
  fetch(`https://rickandmortyapi.com/api/character/?page=${this.state.pageIndex}`)
    .then(res => res.json())
    .then(json => {

        this.setState ({
          isLoaded: true,
          characters: json.results
        })
    });

}

```
  2. Updating

  As well as mounting phase the updating method needs a render.
  The componentDidUpdate() method
  componentDidUpdate is called after any rendered HTML has finished loading. It receives two arguments, the props and state of the component before the current updating period began.
  componentDidUpdate is the best place to perform an interaction with a non-React environment like the browser or making HTTP requests. This should be done as long as you compare the current props to the previous props to avoid unnecessary network requests.
  Here is an example of it in use:

  ```
  class Example extends React.Component {
      [...]
      componentDidUpdate(prevProps, prevState) {
        if (this.props.input == prevProps.input) {
          // make ajax calls
          // Perform any other function
        }
      }
      [...]
    }
  ```



  3. Unmounting (delete):

In this step we don't render anything because the component will be deleted.
The componentWillUnmount() method
This is the only unmounting method. componentWillUnmount is called right before a component is removed from the DOM. This is where you can perform any cleanups that should be done such as invalidating timers, canceling network requests, removing event listeners or canceling any subscriptions made in componentDidMount.

```
class Example extends React.Component {
  [...]
  componentWillUnmount() {
      document.removeEventListener("click", SomeFunction);
  }
  [...]
}
```


# React Fragments:

We wrap the return inside React Fragment to avoid using unnecessary divs, this doesn't appears in the HTML and can't be used to put styles in the element.

```
render() {
  return (
    <React.Fragment>
      <ChildA />
      <ChildB />
      <ChildC />
    </React.Fragment>
  );
}

```
