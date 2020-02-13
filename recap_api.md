
# API (with FETCH, without Axios) 

In App.js 

**fetch("url-de-la-api.com")**     >>  returns the API
**console.log(fetch("url-de-la-api.com")**  >> if we want to display the details in the console to check if the link is well returned and to see how it is returned (to know how to catch every single element of the API for exemple).

**Promise -**
Sometimes the "fetch" does not work (ex : if an information in the url is false or if anything wrong happens during the download). That is why the "result" of the fetch is called a "Promise" : **a promise is a return that can return a success (= the download has worked well) or a fail (the download didn’t work).**
```javascript 
// FETCH METHOD
  componentDidMount() {
     fetch('https://api.github.com/users/?city=Barcelona&month=LastMonth')
       .then(response => response.json())
       .then(info =>
         this.setState({
           data: info,
           isDataLoaded: true,
         })
       )
   }
```
**.then** - to describe an action to do AFTER the success of a promise.
ex : .then(res => res.json())  >> ask to return the API with a json format. **It is a promise** again because this step can return an error (if the doc is with a format that cannot be returned in a json).
AFTER EVERY single PROMISE : write a ".then" to return the success of a promise. 


## GOOD (and almost indispensable!!!) PRACTICE FOR THE USER EXPERIENCE :
using **“catch”** to return and display to the user something else than an error in case of a fail of a promise (ex : we can display a friendly message instead of the original 404 error). We write it at the same level as the first "then" :

```javascript 
.catch(error => {
    console.log(error)      
//if we want to display the error details in the console (to           understand it : this is only for the webdeveloper)
this.setState({
    error: error 
})	//instead of "error: error" we can also write only "error"
})  
```
We use the result of the error to return a friendly message. ex : “We are sorry, we are not able to identify you”.

**isLoading key (in the state)** - to prevent the user that something in being downloadedin case of a success promise that would take time to be downloaded (instead of letting a white page)

in state : isLoading: true            >>> At the moment of the action the API is being downloaded. it is not downloaded yet.
in setState : isLoading: false     >>> Means the download is finished
in render () : define what you want to return to the user if the download is being made and once it is finished (ex : do you want to display a message, a waiting circle..?).




# API (with Axios instead of FETCH)

Axios aims to avoid all the “.then” steps of the FETCH.

It needs to be downloaded in the project : npm install axios
It is called the same way as fetch, ex : axios(‘urldelaapi.com’)

ex:
```javascript

async componentDidMount() {
   const data = await axios(‘urldelaapi’)
   console.log(data) 
    // console.log is optional : just to be sure it returns the API  (same as with FETCH)
this.setState({
   error
   isLoading: false
)}
```
## Axios.get()
use this if you want to control more the promises, you can use more methods inside. 
```javascript
// This function loads pokemon data from the Pokemon API
function fetchPokemonJSON() {
  // Feel free to download this HTML and edit it, to use another Pokemon ID
  const pokemonId = 1;
  const url = `https://pokeapi.co/api/v2/pokemon/${pokemonId}`;
  axios.get(url)
    .then(response => response.data) // DIFFERENT FROM FETCH: response.data instead of response.json()
    .then(pokemon => { {
      console.log('data decoded from JSON:', pokemon);


      // Build a block of HTML
      const pokemonHtml = `
        <p><strong>${pokemon.name}</strong></p>
        <img src="${pokemon.sprites.front_shiny}" />
      `;
      document.querySelector('#pokemon').innerHTML = pokemonHtml;
    });
}


fetchPokemonJSON();
```