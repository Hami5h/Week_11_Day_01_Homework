# JS Scope Homework

Go through each sample code and work out what the output will be and explain what happened.

### Episode 1
```js
var name = 'Keith';

var printName = function() {
  console.log('My name is ' + name );
};

printName();
// The name Keith will be printed
```

### Episode 2
```js
score = 5;

var result = function() {
  var score = 3;
  return score;
};

console.log(result());
// The result will be 3 as 3 is within the result function.
```

### Episode 3
```js
var myAnimals = ['Chickens', 'Cats', 'Rabbits'];

var listAnimals = function() {
  myAnimals = ['Ducks', 'Dogs', 'Lions'];
  for(var i=0;i<myAnimals.length; i++){
    console.log(i + ": " + myAnimals[i]);
  }
}

listAnimals();
// This will output the Ducks, Dogs, and Lions, as they are within the function. It will also output their respective index positions.
```

### Episode 4

```js
var suspectOne = 'Jay';
var suspectTwo = 'Val';
var suspectThree = 'Keith';
var suspectFour = 'Rick';

var allSuspects = function() {
  var suspectThree = 'Harvey'
  console.log('Suspects include: ' + suspectOne + ', ' + suspectTwo + ', ' + suspectThree + ', ' + suspectFour)
  // This will print out jay, Val, Harvey and Rick, since they are all within the function.
};

allSuspects();
console.log( 'Suspect three is:' + suspectThree );
// This will print out Keith, since Keith is declared above, which is outwith the inner function where Harvey is used.
```

### Episode 5

```js
var detective = {
  name : 'Ace Ventura',
  pet : 'monkey'
};

var printName = function(detective) {
  return detective.name
};
// This will return 'Ace Ventura'.

var detectiveInfo = function() {
  detective['name'] = 'Poirot'
  return printName(detective);
};

console.log(detectiveInfo());
// This will return Poirot since the method is modifying the name. In addition the pet will not be printed since the pet is not part of the function.
```

### Episode 6
```js
var murderer = 'rick';

var outerFunction = function() {
  var murderer = 'marc';
  // marc will be updated to valerie as it's within the same scope as the inner function.

  var innerFunction = function() {
    murderer = 'valerie';
  }
  // As the murderer valerie has no var it will set the value above.

  innerFunction();
}

outerFunction();
console.log('the murderer is ', murderer);
// this will return 'Rick as the murderer. Valerie cannot go past marc, since marc is function scoped'
```

### Episode 7 - Make up your own episode/s!

Make up your own episode which can be whatever you wish and the rest of the class will work out together what happened and what the output will be.
