**.sort ( ) Javascript Array Method**
-------------
**.sort( )** is a method that sorts elements within an array in ascending or descending order. The original array is not modified, a re-ordered array is returned.

----------

### Context

Some examples of when you would use the **.sort ( )** method would be:
- When wanting a list of names in alphabetical order
- Having a list of numbers which need to be ordered from smallest to biggest (or) biggest to smallest.
- When you are trying to sort/order a range of information.

### Implementation

```
arr.sort( )
arr.sort(compareFunction)
```
The first example would sort the array in Unicode, for example:

```
> var points = [40, 100, 1, 5, 25, 10];
> points.sort();
< [1, 10, 100, 25, 40, 5]
```
The second example with the inclusion of 'compareFunction', sorts depending on what function is passed in, for example:
```
> var points = [40, 100, 1, 5, 25, 10];
> points.sort(function(a, b){return a-b});
< [1, 5, 10, 25, 40, 100]
```
Sorting strings alphabetically:
```
> var fruits = ["Avocado", "Watermelon", "Peaches", "Mango"];
> fruits.sort();
< ["Avocado", "Mango", "Peaches", "Watermelon"]
```

In the first example the array is sorted via the first numerical digit, whereas in the second example it is sorted by the whole numerical value of the integer.

### Potential Pitfalls

- By default the **.sort( )** method sorts by Unicode (as explained above); which is often not a desirable outcome when sorting integers.

----------

### Further Reading

JavaScript Array sort() Method by w3schools:
https://www.w3schools.com/jsref/jsref_sort.asp

Array.prototype.sort() by Mozilla Developer Network:
https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Array/sort?v=example
