## What is .prototype?

All objects have properties associated with them. '.prototype' allows additional properties and methods to be added to a parent object/class or existing methods/properties to be modified.

## Why would I use this?

Nearly all objects in JavaScript are instances of Object; a typical object inherits properties (including methods) from Object.prototype.
Changes to the Object prototype object are seen by all objects through prototype chaining, unless the properties and methods subject to those changes are overridden further along the prototype chain.  This provides a very powerful although potentially dangerous mechanism to override or extend object behavior.

## How do I implement .prototype?

Don't. Although if you really need to, you can implement it like this:

``` javascript
class Person(first, last, age,) {
   this.firstName = first;
   this.lastName = last;
   this.age = age;
}
Person.prototype.name = function() {
   return this.firstName + " " + this.lastName
};
var myFather = new Person("John", "Doe", 50);
console.log(myFather.name)
```
The above will output "John Doe".

## What are the potential pitfalls of using this?

Please see above regarding dangerous and powerful. Altering the object from the very top of the prototype chain is risky because the changes will all inherently filter down to the bottom.
Altering inbuilt classes may have unintended results for your entire program.

## Alternatives

Create your own classes and fill in the property/method when it's initialised.

## Further Reading
- https://developer.mozilla.org/en/docs/Web/JavaScript/Reference/Global_Objects/Object/prototype
- http://stackoverflow.com/questions/8433459/js-why-use-prototype
- https://www.w3schools.com/js/js_object_prototypes.asp
