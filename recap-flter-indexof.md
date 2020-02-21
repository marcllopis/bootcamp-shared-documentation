## onSubmit() Method with forms and event.preventDefault()


## IndexOf() Method
The indexOf() method searches the array for the specified item, and returns its position( the index).
If the item is not found it will return -1.
If the item is present more than once, the indexOf method returns the position of the first occurence.
Note: The first item has position 0, the second item has position 1, and so on.

Syntax :
```javascript
 arr.indexOf(searchElement[, startIndex])
 ```

Note : <br>
The startIndex is OPTIONAL( specify from what index it's starting the search) <br>
! if it's not specified it will start searching from the start(from index=0).

Exemple:
```javascript
var fruits = ["Banana", "Orange", "Apple", "Mango", "Banana", "Orange", "Apple"];
var a = fruits.indexOf("Apple", 4);
//display 3
```

indexOf() compares searchElement to elements of the Array using the same method used by the === or triple-equals operator 

Exemple:Finding if an element exists in the array or not and updating the array
```javascript
function updateVegetablesCollection (veggies, veggie) { 
if (veggies.indexOf(veggie) === -1) { 
veggies.push(veggie); 
console.log('New veggies collection is : ' + veggies); 
} else if (veggies.indexOf(veggie) > -1) { 
console.log(veggie + ' already exists in the veggies collection.'); 
} 
} 
var veggies = ['potato', 'tomato', 'chillies', 'green-pepper'];
 updateVegetablesCollection(veggies, 'spinach'); 
// New veggies collection is : potato,tomato,chillies,green-pepper,spinach updateVegetablesCollection(veggies, 'spinach'); // spinach already exists in the veggies collection
```

## Filter Method

This array method is used for create a copy of your array with elements that pass the condition.

For example like in the quest we want to pass to the state onli the simspon data chatacter we need to do a filter with the condition inside that the string of characters name includes "Simpson":

```java script 
 let simpson = this.state.quoteList.filter(character =>
      character.character.includes('Simpson')
    );
    this.setState({ quoteList: simpson });
```
So in the filter you are doing a loop as same as map but creating from that loop another array. In each iteration you check if this element pass the condition and if it pass you seve it in the new array.

For this looping you creat a variable for the function of map in this case we named character, so it is as every character of the state array. Then you say that inside this character you look for a element named character(that this is in the state every element) and the pass your condition.
The result will be only the simpson character.

## Reduce() Method