# Fundamentals Part 2 

Part 2 goes over:
1. Strings
2. Conditionals

# Strings (mdn web docs)

**Strings** are a piece of text. JS contains many features for:
- manipulating strings
- creatings custom prompts/welcome messages
- showing the right text labels
- sorting terms in desired order

## Strings - the basics

### Creating a string
- use `let`, `var`, or `const` keywords to declare string type variable
- initialize string value using **quotes** (not doing so creates an error)
- like number variables, can copy other variable values to other values

````
const string = 'The revolution will not be televised.';
console.log(string);

const badString1 = This is a test; // these are all errors
const badString2 = 'This is a test;
const badString3 = This is a test';

const badString = string;  // copying string into badString
console.log(badString);
````

### Single quotes vs. double quotes
- both single/double quotes can be used to wrap strings
- no difference between two, your preference
- just be wary of using quotes in the string when wrapping
- **IMPORTANT:** you **cannot** include the same quote mark inside the string as the one wrapping them

````
const bigmouth = 'I've got no right to take my place…'; // error as I've contains single quote
````

### Escaping characters in a string
- To fix the problem above, we can use a **backslash before the character** we want to escape to **recognize it as text**.

````
const bigmouth = 'I\'ve got no right to take my place…';
console.log(bigmouth);
````

## Concatenating strings
- Concatenate = join together
- done by using **template literal**
### **template literal:** 
- looks like a normal string but it uses backtick characters (`)
- can insert variables by wrapping them inside **${}** characters
````
const greeting = `Hello`; // Example 1: template literal only string

const name = 'Chris'; // Example 2: template literal w/ string and variable
const greeting = `Hello, ${name}`;
console.log(greeting); // "Hello, Chris"

const one = 'Hello, '; // Example 3: tempalte literal w/ two variables
const two = 'how are you?';
const joined = `${one}${two}`;
console.log(joined); // "Hello, how are you?"
```` 

### Concatenation in context
````
const button = document.querySelector('button');

function greet() {
  const name = prompt('What is your name?');
  alert(`Hello ${name}, nice to see you!`);
}

button.addEventListener('click', greet);
````
- first line declares button using querySelector()
- prompt() function works as user input which is stored is name string variable
- once inputted, alert() send message, which uses the **template literal** format to insert/concatenate the greeting + name variable

### Concatenation using "+"

## Other String Features 

### Numbers vs. strings
