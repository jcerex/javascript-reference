## Closures

A closure is a function defined inside another function, where the inner function has access to the lexical environment/execution context in which it was created - in other words, the inner function has access to the outer function's parameters and variables.

Simple example: 

    function person(firstName, lastName) {
    
        function fullName() {
            console.log(firstName + " " + lastName);
        }
        fullName();
    }
    person('Alex', 'Rapley');

### Context 

---

### Implementation Walkthrough/Examples
### Function Factories
    
	function makeAdder(x) {
	  return function(y) {
	    return x + y;
	  };
	}

	var add5 = makeAdder(5);
	var add10 = makeAdder(10);

	console.log(add5(2)); // 7
	console.log(add10(2)); // 12

    
### Namespacing private functions

	var dwightSalary = (function() {
 	  var salary = 60000;
	  function changeBy(amount) {
	    salary += amount;
	  }
	  return {
	   raise: function() {
	   changeBy(5000);
	   },
	   lower: function() {
	   changeBy(-5000);
	   },
	   currentAmount: function() {
	   return salary;
	   }
	  }; 
	})();
    
	alert(dwightSalary.currentAmount()); // $60,000
	dwightSalary.raise();
	alert(dwightSalary.currentAmount()); // $65,000
	dwightSalary.lower();
	dwightSalary.lower();
	alert(dwightSalary.currentAmount()); // $55,000

	dwightSalary.changeBy(10000) // TypeError: undefined is not a function


### Potential Pitfalls:

Memory leaks

### Alternatives:
Callbacks vs. Closures:
* Basically, the callback is like a function pointer (map etc). The bit that makes it a closure, is     when that function accesses anything on the context where it lives, like variables outside it.


Further Readings:
http://javascriptissexy.com/understand-javascript-closures-with-ease/
https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-closure-b2f0d2152b36
https://medium.com/written-in-code/practical-uses-for-closures-c65640ae7304
http://stackoverflow.com/questions/615907/how-is-a-closure-different-from-a-callback
