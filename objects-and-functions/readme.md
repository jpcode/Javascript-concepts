# Objects

Functions and objects are very related..

A simple definition would be: An object contains values.

But, what kind of values are? 

Objects have properties and methods.
//buscar otro ejemplo -- filtro
```javascript
	var ninja = {
		name : 'Jp',
		figth : function(){
					console.log('ya ya ya');
				},
		preferences: {
						"food" : "causa",
						"brand-car": "bmw"
					 }
	}

```


Let's practice with some examples:

```javascript
	var ninja = new Object();
    
    ninja["name"] = "John";
    ninja["skill"] = "Box"

    console.log( ninja );
    var attribute = "name";
    console.log( ninja[ attribute ] );
  	console.log( ninja.name , ninja.skill );

  	ninja["preferences"] = {
  		race : "Chutana",
  		box : "Street",
  		food: "Causa"
  	}

  	console.log( ninja.preferences.race );
  	console.log(ninja["preferences"].race);
  	console.log(ninja["preferences"]["box"]);
  	console.log(ninja.preferences["food"]);

```

Further reading:
https://www.iqaat.com/tech/classes/understand-javascript/Operator-Precedence-In-Javascript.pdf
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Working_with_Objects
https://www.quora.com/What-is-object-in-javascript


# Functions are objects?

In Javascript Functions are objects.

First Class functions: anything that you can do with other types you can do with functions, they can make a dangerours way for programmers or in the other side, a fantastic way to solve problems.

Functions are special type of object can contain:
Primitives, Object, function, name ( optional - can be anonymous ), code.

The code that you write is just other propertie.


```javascript
  function hi(){
    console.log('hi');
  }

  hi.speak = 'Spanish';

  console.log( hi );
  console.log( hi.speak );

```

At this time, you can see functions as more than a container of code, it's a object.

# Functions statements and expressions.

## Expression

A unit of code that result in a value

```javascript
  
  var end;
  end = 5; // returns 5
  1 + 2;   // return 3
  start = { end : 'saturday'}

  //statement just works and expressions return a value
  var value = if ( x == 4 ){};

  //function statement
  sum(2,3);
  function sum( a, b ){
    return a + b;
  }

  //function expression
  var s = function( a,  b ){
      return a + b;
  }
  s();

  // what happen if you move s() to the top? 

  s();
  var s = function( a,  b ){
      return a + b;
  }

  // Functions expressions are not hoisted.

  //let's explore 

  function print(){

  }

```
# This keyword

```javascript
  
    // inside the browser, the global object is windows
    console.log( this );

    function foo(){
        console.log( this );
    }

    var bar = function(){
        console.log( this );
    }
    foo();
    bar();

    function foovar(){
        this.age = 15;
    }

    foovar();
    console.log( age );

    // object method
    // if a value is a primitive is a property and if a value is function is a method.
    var car = {
        brand : 'BMW',
        run: function(){
            //var self = this;
            console.log( this );
            /*
            var updateBrand = function( b ){
                this.brand = b;
            }

            updateBrand('AUDI');
            console.log( this );
            */
        }

    }
    car.run();

    // We learn ... ?

```
=
# Arguments

There are the parameters you pass to a function , arguments = parameters.


```javascript
  
    function sum3( a, b, c ){
        console.log( a );
        console.log( b );
        console.log( c );
        console.log( arguments );
        /*
            arguments are called array-like
            if ( arguments.length === 0 ){
                console.log('Missing parameters');

            }else{
                console.log( arguments[ 0 ] );
            }
            // in short time arguments will be deprecated.
            // Spreads...

        */
    }

    sum3(); // in other languages is an error.
    sum3(2);
    sum3(2,3);
    sum3(2,3,4);

    /* In the next version of javascript we can define default values in parameteres 

        function add( a = 2, b = 3){
            return a + b;
        }
        add();
    */

    // research for : function overloading like c++;

```

# IIFE
Inmediately Invoked functions expressions

```javascript
    
    var endClass = function(){
        var d = new Date();
        console.log('finish: ', d );
    }
    // at this part we have a function object
    // let's invoke:

    var endClass = function( student ){
        return "Congrats! " + student;
    }('Jp'); // this invokes the function inmediately after create it.

    // executing code in the fly.
    function(){
        console.log('done');
    }

    (function(){
        console.log('done');
    });

    //inside
    (function(){
        console.log('done');
    }());

    //outside
    (function(){
        console.log('done');
    })();
    // Just pick one.

```

Benefits: 
 - Reduce scope lookups
 - Readability

further reading:
http://gregfranko.com/blog/i-love-my-iife/
https://www.quora.com/Javascript-where-to-place-an-IIFE

# Closures

At this time you know:
 - First Class functions
 - Execution stack
 - Execution context

There are the pre-requisites to understand closures.

```javascript
    
    function finish( a ){
        return function( b ){
            console.log( a + ' ' + b );
        }
    }

    //finish('Js')(new Date());

    var endCourse = finish('js');
    endCourse(new Date());
    // closure are feature of JS.

    function test(){
       var a = [];  
       for ( var i = 0; i < 3; i++ ){
           (function( y ){
            a.push(function(){
              console.log(y);
            })  
           }( i ));
        }
      a[0]();
      a[1]();
      a[2]();
    }
    test();

```







