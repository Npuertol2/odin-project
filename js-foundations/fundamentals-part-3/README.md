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
