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

# Logical AND ( && )

```javascript
	
	//---- NON-BOOLEAN ----
	//Returns a if it can be converted to false; otherwise, returns b.

	"hello" && "hi" 
	"testing" && ""
	0 && 1

	//---- BOOLEAN ----
	//Returns true if both operands are true; otherwise, returns false.

	true && true
	false && true
	true && false
	false && false

```

# Logical OR ( || )

```javascript
	
	//---- NON-BOOLEAN ----
	//Returns a if it can be converted to true; otherwise, returns b. 
	"Hello" || "hi"
	"testing" || ""
	1 || 0

	//---- BOOLEAN ----
	//Returns true if either operand is true.
	true || true
	false || true
	true || false
	False || false

```

# Logical NOT (!)

```javascript
	
	//Returns false if a can be converted to true; otherwise, returns true.
	!true
	!false
	!''
	!1

```

Using "!!", what is the difference between ! and !! ?

Double negation turns a truthy or falsy value into a boolean value ( true or false )

```javascript
	
	var guy = {
		age : 25,
		married : 1
	};

	if ( guy.married ){
		// execute something is a guy is married, but in a truthy way.
		console.log( guy.age );
	}

	guy.married === true // this could be trutht or not

	!!guy.married === true // with this you  force a truthy value to be a boolean value

```

# Binary & Bitwise Operators ( Introduction )

Unlike logic operators we reviewed prior, bitwise operators can only be performed on numbers. When we write out our bitwise code, we typically use decimal representation of the number; however JavaScript converts these numbers under the hood to a 32-bit binary representation of the number. 

You should learn , how binary works before to see this section

Further reading: 
https://www.quora.com/How-can-a-computer-understand-binary-code
http://www.kerryr.net/pioneers/binary.htm


# Bitwise AND ( & )

When we use the bitwise AND operator, we compare each digit of binary representations of two numbers, both 32 bits long, and the result will either be a 1 or 0 based on our chart above. When both places have a 1, the output is 1. When one of the two digits is a 0 then the output will always be 0

|  Bit1     | Bit2 | ANDed value |
| ----- | -----| ----- |
| 0 | 0 | 0 |
| 1 | 1 | 1 |
| 1 | 0 | 0 |
| 0 | 1 | 0 |


## Example
|  bits     | Representation   		    |
| ------------- | ------------- |
| bit1 | 00000000000000000000000000001001  |
| bit2 | 00000000000000000000000000000101   |
| result   | 00000000000000000000000000000001   |


# Bitwise OR ( | )
 when we do the OR operation, we compare each place of the two numbers. Except this time if there is at least one 1 then the output will be one.

|  Bit1     | Bit2 | ORed value |
| ----- | -----| ----- |
| 0 | 0 | 0 |
| 1 | 1 | 1 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |

## Example
|  bits     | Representation   		    |
| ------------- | ------------- |
| bit1 | 00000000000000000000000000001001  |
| bit2 | 00000000000000000000000000000101   |
| result  | 00000000000000000000000000001101   |

# Bitwise XOR (^) 
XOR means exclusive OR. When one, and only one, of the expressions has a 1 in a digit, the result has a 1 in that digit. Otherwise, the result has a 0 in that digit.

|  Bit1     | Bit2 | XORed value |
| ----- | -----| ----- |
| 0 | 0 | 0 |
| 1 | 1 | 0 |
| 1 | 0 | 1 |
| 0 | 1 | 1 |

## Example
|  bits     | Representation   		    |
| ------------- | ------------- |
| bit1 | 00000000000000000000000000001001  |
| bit2 | 00000000000000000000000000000101   |
| result  | 00000000000000000000000000001100   |

## Bitwise NOT (~)

Any digit that is a 1 in the expression becomes a 0 in the result. Any digit that is a 0 in the expression becomes a 1 in the result.

|  Bit1     | NOT |
| ----- | -----| 
| 0 | 1 | 
| 1 | 0 | 
| 1 | 0 | 
| 0 | 1 | 

## Example
|       | Representation   		    |
| -------- | ------- |
| Bit | 00001001 |
| ~Bit | 11110110 |