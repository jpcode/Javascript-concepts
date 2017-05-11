# Execution Context and Lexical Environments

# Idea
What happen with your code? 

## Syntax Parser
Is a program that reads your code and determines what it does and if its grammar is valid.

- Compilers
- Interpreters

Code:
```javascript

function sayHi(){
	var hi = 'Hi!!';
}

```
Computer Instructions:

Function
	Variable


Further reading:
 - https://www.quora.com/How-does-parsing-work
 - https://softwareengineering.stackexchange.com/questions/138521/is-javascript-interpreted-by-design
 - https://www.quora.com/What-is-the-difference-between-a-compiler-and-an-interpreter/answers/7670223


## Lexical Environments
 Where it's written and what surrounds it.

 Further reading:
 http://es5.github.io/#x10.2


## Execution Context

A Wrapper to help manage the code that is running.

Hoisting: 

```javascript
	/* First Scenario */
	var a = 'Hello Lab';

	function b(){
		console.log('called');
	}

	b();
	console.log(a);

	/* Second Scenario */

	b();
	console.log(a);

	var a = 'Hello Lab';

	function b(){
		console.log('called');
	}


	/* Third Scenario */

	b();
	console.log(a);

	function b(){
		console.log('called');
	}

```
Hosting Definition:

Setup Memory Space for variables and functions before your code begins to be executed line by line.

** All variables in Javascript are initially set to undefined.

Life Cycle:
- Creation: ( Parse is running and recognize where you've created variables and where you've created functions ).
    - Variables, functions is created ( Global Object is created )
    - "this" is determined
    - Outer Environment
    - Hoisting
- Execution ( line by line )
	- Code is interpreted
	- Executed

Let's understand with an example:

```javascript
	  function sayHi( name ){
	   	var hi = 'Hello my friend!';
	   	var say = function(){
	   		alert( hi );
	   	};
	   	function foo(){};
	  }
	  sayHi('Jp');
```
Let's create execution contex for this example:

```javascript
	ecSayHi(){
		variableObject : {
			arguments: {
	           0: 'Jp',
	           length: 1
		    },
		    name: 'Jp',
		    f : a pointer memory to "f" function
		    hi : undefined,
		    say: undefined
	    },

	   scopeChain : {},
	   thisForSayHi : {}
	}
```

**The call stack is a collection of execution context.

## undefined
```javascript

 /* Scenario 1: */ 

var myVar;
console.log( myVar );

/* Scenario 2: */

console.log( myVar2 );

```

Undefined is the same as Not defined? --- No.

Internally Undefined means: The variable hasn't been set. Is a special keyword/value.

Scenario 1 : 

```javascript
var a;
console.log(a);

if ( a === undefined ){
	console.log('a is undefined' );
}else{
	console.log('a is defined');
}

```

Scenario 2: 

```javascript

console.log(a);

if ( a === undefined ){
	console.log('a is undefined' );
}else{
	console.log('a is defined');
}

```

Never do this:
```javascript
var a = undefined;
```

Scenario:

```javascript

var a;
console.log(a);

if ( a === undefined ){
	console.log('a is undefined' );
}else{
	console.log('a is defined');
}
```

Is difficult to debug, althought you don't know if is undefined because your set it or because JS engine set it.


## Execution Phase detail

```javascript

function b(){
	console.log('called b');
}

b();
console.log(a);
var a = 'Hello Lab';
console.log(a);
```

In creation Phase:
function is set up and var "a" as set up with a value of "undefined"

Execution Phase:

```javascript

b(); /* is executed and runs that function */
console.log(a) /* is executed and print the value to console ("undefined") */
var a = 'Hello Lab' /* is executed and set the value in memory of a to the stirng Hello World */
console.log(a) /* is executed */

```


Further reading
https://dzone.com/articles/javascript-execution-context

