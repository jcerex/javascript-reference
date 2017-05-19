# Reduce Method

The .reduce method, in its simplist form, reduces a given array to a single value!

# Context

You want to use the reduce method when you have an array of elements (numbers or words) that you want to implement a function too (add/minus/or other exciting functions)!
Some examples where you may want to use it:
- adding up the total revenue for an ecommerce store based on the selling price of each product they sold!
- adding up the number of rocket launches in 2017

```
array.reduce(callback, [initialValue])
```

## Parameters

### Callback
Function to execute on each element in the array, taking four arguments:

- accumulator
The accumulator accumulates the callback's return values; it is the accumulated value previously returned in the last invocation of the callback, or initialValue, if supplied (see below).

- currentValue
The current element being processed in the array.

- currentIndex
The index of the current element being processed in the array. Starts at index 0, if an initialValue is provided, and at index 1 otherwise.

- array
The array reduce was called upon.

### InitialValue
[Optional] Value to use as the first argument to the first call of the callback. If no initial value is supplied, the first element in the array will be used. Calling reduce on an empty array without an initial value is an error.

# Implementation and examples

Let's explore this through some examples then:

```
var numbers = [15, 3, 1, 6, 5];

var sum = numbers.reduce(
  function(total, amount)
  {
  return total + amount
});
```

- In this example, the reduce method accepts two parameters, the total and the current amount.
- The reduce method cycles through each number in the array much like it would in a for-loop.
- When the loop starts the total value is the number on the far left (15) and the current amount is the one next to it (3).
- In this particular example, we want to add the current amount to the total.
- The calculation is repeated for each amount in the array, but each time the current value changes to the next number in the array, moving right.
- When there are no more numbers left in the array the method returns the total value.

We can also write the above example using the fat-arrow:

```
var numbers = [15, 3, 1, 6, 5];

var sum = numbers.reduce(
  (total, amount) => total + amount,
  0
);
```

Or for more clarity, you might like to see the above examples by being broken down into two functions:

```
var numbers = [15, 3, 1, 6];

function getSum(total, num) {
    return total + num;
}
function myFunction(item) {
    return numbers.reduce(getSum, 0);
});
```

And if you were wondering how the reduce method can be used on words:

```
var animals = ["cat","dog","fish"];
var total = animals.reduce(function(sum, word) {
  return sum + word.length;
}, 0);
console.log(total)
```

## Exciting Usages
For more exciting uses, we can use reduce to flatten nested amounts into a single array.
We set the initial value to an empty array and then concatenate the current value to the total.

```
const data = [[1, 2, 3], [4, 5, 6], [7, 8, 9]];
const flat = data.reduce((total, amount) => {
  return total.concat(amount);
}, []);
flat // [ 1, 2, 3, 4, 5, 6, 7, 8, 9 ]
```

More often than not, information is nested in more complicated ways. For instance, lets say we just want all the favourite colors in the data variable below.

We’re going to step through each object and pull out the colours. We do this by pointing amount.color for each object in the array. We then use a forEach loop to push every value in the nested array into out total.

```
const music_station = [
  {song: 'happy', artist: 'pharrel williams', color: ['blue','green']},
  {song: 'changes', artist: 'tupac', color: ['green','black','orange','blue']},
  {song: 'gold digger', artist: 'kanye west', color: ['green','red']}
];

const colors = data.reduce((total, amount) => {
  amount.color.forEach( colors => {
      total.push(colors);
  })
  return total;
}, [])
colors //['blue','green','green','black','orange','blue','green','red']
```

# Pitfalls

The Reduce method is not very intuitive to understand as the parameters it accepts can be confusing to some. Also, on the surface of it all - it doesn't seem that powerful...but oh my have you got something to look forward to! :)

Some silly mistakes to avoid however are that:

- If you don’t pass in an initial value, reduce will assume the first item in your array is your initial value. This worked fine in the first few examples because we were adding up a list of numbers.
- If you’re trying to tally up fruit, and you leave out the initial value then things get weird. Not entering an initial value is an easy mistake to make and one of the first things you should check when debugging.
- Another common mistake is to forget to return the total. You must return something for the reduce function to work. Always double check and make sure that you’re actually returning the value you want.

# Alternatives

In 2011, JavaScript introduced **map**, **reduce**, and **filter** as powerful alternatives when translating elements, finding cumulative values, or building subsets based on conditions. These methods help the developer manage less complexity, work without side effects, and often make code more readable.

# Further Reading
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/Reduce?v=example
- https://medium.freecodecamp.com/reduce-f47a7da511a9
