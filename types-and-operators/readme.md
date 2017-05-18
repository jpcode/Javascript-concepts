# Types

How javascript deal with types? 

There are some programming languages that you need to define what type each variable is, that is called static typed. Where compiler do the type checking process and will detect bugs early. Examples: Java, C, C++.

```C
	int a;
	bool mybool = 'noway'; // an error
```

In the other hand, exists languages that uses Dynamic Typing like  perl, javascript where type checking occurs when code is interpreted.

```javascript
	var bool = true;
	bool = 'hi'; // no errors
	bool = 123;
```

Further reading:

https://www.quora.com/What-is-the-difference-between-a-dynamically-typed-and-a-statically-typed-programming-language


## Primitive types
What primitive type means?
A type of data that represents a single value.

- Undefined : Lack of existence ( Don't use a initially value, see "Execution Context topic")
- Null : Lack of existence ( you can use to set to nothing )
- Boolean: It can be true or false.
- Number: This is the only one numeric type in javascript and its a floating point number, other language have integer, float, double, etc. So imagine what are some restriction related to this behavior.
- String:  a Sequence of characters you can use a simple quotes or double quotes to set it.
- Symbol ( ES6 ) : A inmutable type that you can use as identifiers.

Further reading:
https://developer.mozilla.org/en-US/docs/Glossary/Symbol

## Operator
Is a special function that is written differently.
Examples:
```javascript
	var s = 1 + 2;
	console.log( s ); // 3
```

How JS engine do "1+2"?
Remember syntax parser...

In Javascript as other languages provides the option to write in infix notation.

# Infix
Placement of operators between operands 

```javascript
	// prefix:
	+ 1 2;
	// postFix
	3 4+
	// infix ( Human readable )
	3 + 4 
```

Further reading:
https://en.wikipedia.org/wiki/Infix_notation

# JS logic operators in JS.

|  Operator     | Usage		    |
| ------------- | ------------- |
| Logical AND  	| a  && b       |
| Logical OR	| a  || b       |
| Logical NOT   | !a            |

# Truthy and Falsy

 Like most computer languages, JavaScript supports Boolean data types; values which can be set to true or false. In addition, everything in JavaScript has an inherent Boolean value, generally known as either truthy or falsy. Handling truthy and falsy values can be a little quirky, especially when comparing variables. Understanding some of the more bizarre rules can help when debugging complex client-side applications. Let’s see if we can predict the whether or not the following evaluate as true or false!

```javascript
	
	if (true)

	if (false)

	if (-3.14)

	if (3.14)

	if ("foo")

	if (undefined)

	if ([])

	if ('')

	if (NaN)

```

Further reading:
https://developer.mozilla.org/en-US/docs/Glossary/Boolean
https://developer.mozilla.org/en-US/docs/Glossary/Falsy
https://developer.mozilla.org/en-US/docs/Glossary/Truthy


# Truthy and Falsy Table

|  Truthy: evaluates to true      | Falsy: evaluates to false		    |
| ------------- | ------------- |
| if (true) | if (false) |
| if ({}) | if (null) |
| if ([]) | if (undefined) |
| if (42) | if (0) |
| if ("foo") | if (NaN) |
| if (new Date()) | if ('') |
| if (-42) | if ("") |
| if (3.14) | |
| if (-3.14) | |
| if (Infinity) | |
| if (-Infinity) | |