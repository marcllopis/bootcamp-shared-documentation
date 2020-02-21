# The Reduce Method

## Definition 

As the name already indicates, the reduce method is used, to **reduce** an array to one single value.
It traverses a given array from left to right, execuding a function (that has to be written) for each
element of the array.
The method uses a so called accumulator to "collect"/store the return value in. 
Since *reduce* does'nt change the original array, a new array shoulb be created, in order to receive the
desired values.

## Usage 

### Get the sum of an array

A kind of standart example to use the method would be to get the sum of an array of numbers: 

```javascript 

        const newNumbers = [1, 3, 5, 7];

        const newSum = newNumbers.reduce((accumulator, currentValue) => {
        
                console.log('The value of accumulator: ', accumulator);
                console.log('The value of currentValue: ', currentValue);
                return accumulator + currentValue;
                }, 10);

        console.log(newSum)

```
In the given exapample you can recognize pretty well how the method works.

### Acumulating the number of letters

The following example shows how *reduce* can be applied to look for the number of 
duplicates of letters in a given array:

```javascript 

   const duplicates = (frequency, letter) => {
        frequency[letter] = frequency[letter] +1 || 1;
        return frequency;
      }
 
   const letterCounting = (str)  => {

        let count = str.toLowerCase().split('').reduce(duplicates, {})
                   
        return count;       
        };

```

