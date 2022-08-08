# JS Fundamentals Part 3

This lesson teaches how to:
1. define and invoke different kind of functions
2. use the return value
3. explain function scope

# Functions - mdn web docs

## Built in browser functions
Examples include 
1. **.replace()**
````
const myText = 'I am a string';
const newString = myText.replace('string', 'sausage');
console.log(newString);
````
2. **.join()**
````
const myArray = ['I', 'love', 'chocolate', 'frogs'];
const madeAString = myArray.join(' ');
console.log(madeAString);
````

- **invoke** - means to run/execute function

## Functions versus methods

- **methods** - are functions that are **part of objects**
- **custom functions** - defined in our code and not inside the browser

## invoking functions
- after a function is defined, invoking it is done by
    - including name of function followed by parentheses
````
function myFunction() {
  alert('hello');
}

myFunction();
// calls the function once
````

## Function parameters
- some functions require parameters to be specified within the parentheses made when invoking it (ex. **replace()**)
- some don't (ex. **Math.random()**)

### optional parameters
- some functions have a default behavior when not specifying anything within parameters (**ex. join()**)
    - comma is used by default if nothing is specified as delimiter

````
const myArray = ['I', 'love', 'chocolate', 'frogs'];
const madeAString = myArray.join(' ');
console.log(madeAString);
// returns 'I love chocolate frogs'

const madeAnotherString = myArray.join();
console.log(madeAnotherString);
// returns 'I,love,chocolate,frogs'
````

### default parameters
- default parameters can be specified in parentheses when first creating the function
- now, when function is called without parameters, the default parameter will be used

````
function hello(name='Chris') {
  console.log(`Hello ${name}!`);
}

hello('Ari'); // Hello Ari!
hello();      // Hello Chris!
````

## Anonymous + arrow functions

### Anonymous functions
- **anonymous functions** are functions without names
- can be specified within parameters of another function (seen below)
- when using **addEventListener()**, need to specify:
    - name of event to listen for (keydown for example)
    - and a function to run when event happens
- instead of doing this:

````
function logKey(event) {
  console.log(`You pressed "${event.key}".`);
}

textBox.addEventListener('keydown', logKey);
````
- you can use **anonymous functions** to do this:
````
textBox.addEventListener('keydown', function(event) {
  console.log(`You pressed "${event.key}".`);
});
````

### Arrow Fucntions
- **arrow functions** are an alternative form of **anonymous functions**
- SYNTAX: (event) => : 
````
textBox.addEventListener('keydown', (event) => {
  console.log(`You pressed "${event.key}".`);
});
````
- curly brackets can be omitted if it is only one line

````
textBox.addEventListener('keydown', (event) => console.log(`You pressed "${event.key}".`));
````
- parameter parentheses can be taken out if there is only on parameter

````
textBox.addEventListener('keydown', event => console.log(`You pressed "${event.key}".`));
````

## Function Scopes and conflicts
- **scope** - levels that define accessibility of variables and things within your code
  - global scope - top level. variables here are accessible from everywhere in your code
- it is best practice to **keep parts of code such as variables locked away in functions** to avoid scope conflicts.
  - kind of like a zoo
    - all animals in zoo are kept in separate enclosures
    - only allowed to use certain things in their enclosures
    - having them go into other enclosures would be a problem


# Function Return values - mdn web docs

## Alternative default parameters
Instead of using function declaration parameter = something, some alternatives include
1. parameter comparison to undefined
````
function showMessage(text) {
  // ...

  if (text === undefined) { // if the parameter is missing
    text = 'empty message';
  }

  alert(text);
}

showMessage(); // empty message
````
2. || operator
````
function showMessage(text) {
  // if text is undefined or otherwise falsy, set it to 'empty'
  text = text || 'empty';
  ...
}
````
3. *nullish coalescing operator* **??**
````
function showCount(count) {
  // if count is undefined or null, show "unknown"
  alert(count ?? "unknown");
}

showCount(0); // 0
showCount(null); // unknown
showCount(); // unknown
````

# function basics - javascript.info

- a function with **empty return** or without returns **undefined**
- one function/one action -- functions should do exactly what is suggested by name and no more 

# Function Expressions
- Function Declaration
````
function sayHi() {
  alert( "Hello" );
}
````

- Function Expressions are different from Function Declaration

````
let sayHi = function() {
  alert( "Hello" );
};
````
- variable sayHi gets assigned the value of a new function. 
- *create a function and put it into the variable `sayHi`*


## Function is a value

- no matter if we're using expression or declaration, **a function is a value**
- both store a fucntion in the sayHi variable
- alert() can be used to print out the value of sayHi variable

````
function sayHi() {
  alert( "Hello" );
}

alert( sayHi ); // shows the function code, NOTE there is no parentheses after sayHi so it does not run the function
````

### Copying function to another variable
- we can take sayHi() and copy it to another variable
````
function sayHi() {   // (1) create
  alert( "Hello" );
}

let func = sayHi;    // (2) copy

func(); // Hello     // (3) run the copy (it works)!
sayHi(); // Hello    //     this still works too (why wouldn't it)
````
- note the lack of parentheses during the assignment of sayHi to func

### Function Expression = semicolon at the end
- important, since it is not function declaration
- it is recommended as `function(){}` is inside assignment statement `let sayHi = ...`

## Callback functions

- function used to be *calledback* in another function
- these are functions that are passed in as parameters or variables in other functions to be used given a certain case
- example given the function `ask(question, yes, no)`

````
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

function showOk() {
  alert( "You agreed." );
}

function showCancel() {
  alert( "You canceled the execution." );
}

// usage: functions showOk, showCancel are passed as arguments to ask
ask("Do you agree?", showOk, showCancel);
````
- if confirm to question is true, pass yes
- if confirm to question is false, pass no 

### Function expressions in Callback Functions
- instead of using function declarations to make the `showOk` and `showCancel` functions, we can use expressions directly inside the ask() function

````
function ask(question, yes, no) {
  if (confirm(question)) yes()
  else no();
}

ask(
  "Do you agree?",
  function() { alert("You agreed."); },
  function() { alert("You canceled the execution."); }
);
````

## Function declaration vs Function expression

- Function Declaration: 
  - declared as separate statement
  - in main code flow
````
// Function Declaration
function sum(a, b) {
  return a + b;
}
````
- Function expression:
  - created inside an expression / another syntax construction
  - such as right side of assignment expression
````
// Function Expression
let sum = function(a, b) {
  return a + b;
};
````

