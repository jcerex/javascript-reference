# Content(this)
# 1. Executive Summary 
Lets look at the sentence below.
Taka likes to use analogies because it helps ```Taka``` to understand the concepts better.
Using context, the sentence can be written as:
Taka likes to use analogies because it helps ```him``` to understand the concepts better.
- In Javascript, the thing called *this* is the object that "owns" the Javascript code.
- In Javascript, *this* always refers to the "owner" of the function we're executing or, the object that the function is a method of. 
 ## 1. Context 
 - objects
 - functions
# 2. Implementation
```Javascript
 var person = {  
        firstName   :"Taka",  
        lastName    :"Suzuki",  
        showFullName:function () {  
        console.log (this.firstName + " " + this.lastName);  
        }  
    }  
    person.showFullName (); // Taka Suzuki 
```
# 3. Potential Pitfalls
- *this* is bound to another object, if we assign a method that uses *this* to a variable.
- Confusion of what *this* refer to.
# 4. Further Reading
* [http://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/] - HTML enhanced for web apps!
