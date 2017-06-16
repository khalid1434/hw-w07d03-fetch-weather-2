## ES6 Practice!


#### Prompt:
For all the questions below, answer with the shortest possible ES6 solution.


#### Problems:

1. Refactor the code below into ES6:
	```javascript
	var stringSplit = function(phrase){   
		return phrase.split(' '); 
	} 


	console.log(stringSplit('hello world'))
	```



2.  Use the data set below to answer the following 3 questions:
	```javascript
	var myBesties = [
		{ name: "Ron",
			species: "wizard-human"
		}, {
			name: "Hagrid",
			species: "half-giant half-human"
		} , {
			name: "Dudley",
			species: "muggle"
		} , {
			name: "Buckbeak",
			species: "hippogryph"
		} , {
			name: "Hermione",
			species: "wizard-human"
		} , {
			name: "Dumbledore",
			species: "wizard-human"
		} , {
			name: "the Baselisk",
			species: "baselisk"
		}
	]
	```




	1. Refactor the code below into ES6:

	```javascript
	var names = myBesties.map(function(friend) {
		return friend.name
	})

	console.log(names)
	```

	2. Using ES6, return an array of objects that includes only friends that are "wizard-human".


	3. Refactor the code below into ES6:

	```javascript
	function sayEveryOther() {
	  for(var i = 0; i < myBesties.length; i+=2){
	    console.log(myBesties[i]);
	  }
	}

	sayEveryOther()
	```






3.  Refactor the code below into es6:

	```javascript
	var queryButton = document.getElementById('submit-query');


	queryButton.addEventListener('click', function(e) {
	  var userInput = document.getElementById('character-name-input').value;
	  e.preventDefault();
	  $.ajax({
	    url: 'https://swapi.co/api/people/',
	    type: 'GET',
	    data: { search: userInput } // For GET requests, this will give the parameters of the query.
	  }).done(function(resultData) {
	    console.log('result data:', resultData);
	    var resultDisplay = document.getElementById('result-display');
	    $(resultDisplay).toggleClass('awaiting');
	    $(resultDisplay).empty();
	    var newText = document.createTextNode(JSON.stringify(resultData));
	    resultDisplay.appendChild(newText);
	  });

	})
	```