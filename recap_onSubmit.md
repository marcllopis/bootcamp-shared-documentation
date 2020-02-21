# On submit 

In this case, we're explaining the onSubmit method in a React app

When a user clicks on submit button of a form, JavaScript onsubmit event will call a function:

```javascript
render () {
    return(
        <div>
            <form onSubmit={this.handleSubmit}>
                <label htmlFor='name'>Name:
                    <input type ='text' value ={this.state.name} onChange={this.handleChange} >
                    </input>
                </label>
                <input type="submit" value="Submit" />
            </form>
        </div>
    )
}
```
In our example, we call handleSubmit() function on form submission.

```javascript

handleSubmit = event => {
    event.preventDefault();
    this.setState ({
        item: '',
        itemList: [...this.state.itemList, this.state.item]
    })
}

```

And we call handleChange() function when there's a change in the input
```javascript

handleChange =(event) => {
    this.setState({
        name: event.target.value,
    })
}
```
