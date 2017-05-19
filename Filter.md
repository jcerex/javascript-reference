# Summary

`.filter()` is a JS method used to extract items of an array according to a callback function and create a new array out of these items.

## Context

This method can be used in situation where we want to get a particular set of items out of an array. For example, an application that sends mail out to users and they want to send mail out to specific users who are in a particular postcode. The filter method will be able to extract values in an array it is used on and that correspond to the conditions in the callback function.

## Implementation

This is the abstracted syntax:
`var newArray = arr.filter(callback[, thisArg])`

`newArray` - this is the array object with the extracted values.

`arr` - this is the array that is used being 

`callback` - name of the function that has the condition.

`[, thisArg]` - the argument to put into the callback.

### Example of basic implementation:

```javascript
var Address = [2091, 2018, 3094, 2018, 8759, 2018, 2894, 5985, 2094];
var postCode = Address.filter(function(val) {
  return val === 2018;
});
[2018, 2018]
```

#### Explanation

The `Address` array is having the filter method called on it. The argument entered into the filter method is a function which takes a value from the array. This value is checked by a condition in the callback and if it is true the value is put into a new array, here named `postCode`. If it is false it is not entered.

### Example of complex implementation

```javascript
var oldArray = [
    {name: 'Adam', postcode: '2000'},
    {name: 'Bryan', postcode: '2001'},
    {name: 'Charlie', postcode: '2002'},
    {name: 'Firman', postcode: '2011'},
    {name: 'John', postcode: '2078'},
    {name: 'Elise', postcode: '2234'},
    {name: 'Surya', postcode: '2000'},
];
var newArray = oldArray.filter(function(val) {
  return val.postcode === '2000';
});
let printContent = newArray.map((person) => {
    return person.name
});
```

live example http://js.do/code/filterexample

#### Explanation

In this example we are doing the same but we are using a key, value pair such as is commonly used in JSON data. This will exact the objects that have a postcode of 2000 put and them into `newArray`. The `newArray` will have the map method go over it to extract the names into another array and other functions can be performed on that array such as printing them with `document.write(printContent);`.

It must be used on an array object and that array object can contain any type of value such as an object, string, or number.

## Potential WTF's

It cannot take a singular value. If you try to do this:

```javascript
var newArray = arr.filter(anyValue)
```

It will not work and you'll get an `Uncaught TypeError` because the method has to use a callback for the conditions.


## Alternatives

This is an alternative to filter:

```javascript
var oldArray = [
    {name: 'Adam', postcode: '2000'},
    {name: 'Bryan', postcode: '2001'},
    {name: 'Charlie', postcode: '2002'},
    {name: 'Firman', postcode: '2011'},
    {name: 'John', postcode: '2078'},
    {name: 'Elise', postcode: '2234'},
    {name: 'Surya', postcode: '2000'},
     
];
var newArray = [];
 
oldArray.forEach((val) => {
    if(val.postcode === '2000') {
        newArray.push(val);
    }
});
var printContent = newArray.map((person) => {
    return person.name
});
document.write(printContent);

This will return Adam and Surya who have the postcode 2000. 
```
See this live example http://js.do/code/foreachjsexample

### Explanation

This is very similar to the function but there's a bit more involved. Here we are using the `forEach` method on `oldArray` and each value is entered through `val`. This is checked against the if statement for a particular condition and if it is true the value will be push into 'newArray'.

## Further Reading

- https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/filter?v=control

- https://code.tutsplus.com/tutorials/how-to-use-map-filter-reduce-in-javascript--cms-26209
