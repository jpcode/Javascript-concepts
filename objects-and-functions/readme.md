# Objects

Functions and objects are very related..

A simple definition would be: An object contains values.

But, what kind of values are? 

Objects have properties and methods.

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

