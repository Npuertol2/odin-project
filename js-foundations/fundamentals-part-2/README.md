# Fundamentals Part 2 

Part 2 goes over:
1. Strings
2. Conditionals

Assignments include looking at:
1. Strings MDN Tutorial
2. w3schools String Methods
3. String Methods List

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

done by using:const output = 'I like the song.\nI gave it a score of 90%.';
console.log(output);  // I like the song.
                      // I gave it a score of 90%.
1. **template literal**
2. **"+" sign**
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
- another way to concatenate
- template literals are recommended (more readable / clear)

````
const greeting = "Hello"; // "+" Method
const name = "Chris";
console.log(greeting + ", " + name); // "Hello, Chris"

const greeting = "Hello"; // Template Literal Method
const name = "Chris";
console.log(`${greeting}, ${name}`); // "Hello, Chris"
````
## Other String Features 

### Numbers vs. strings
- when converting number --> string using template literal, browser will convert number to string before concatenation
- useful for converting user inputs from form's text fields --> numbers to make useful in other functions

- String --> Number: Use **Number()** function. 
````
const myString = '123';
const myNum = Number(myString);
console.log(typeof myNum); // Number() converts myString from '123' to 123, stores in myNum
````
- Number --> String: Use **toString()** function
````
const myNum2 = 123;
const myString2 = myNum2.toString();
console.log(typeof myString2); // toString() convert myNum2 from 123 to '123', stores in myString2
````

### Including expressions in strings
- By using template literals, **expressions** and **simple variables** can be inserted into variables, showing their results

````
const song = 'Fight the Youth';
const score = 9;
const highestScore = 10;
const output = `I like the song ${song}. I gave it a score of ${score/highestScore * 100}%.`;
console.log(output);  // "I like the song Fight the Youth. I gave it a score of 90%."
````
### Multiline strings
- template literals respect **line breaks** in source code. Therefore, you can use them to **span multiple lines**

````
const output = `I like the song.
I gave it a score of 90%.`;
console.log(output);  // I like the song.
                      // I gave it a score of 90%.
````

- in regular strings, you would need to use line break characters **\n** in the string

````
const output = 'I like the song.\nI gave it a score of 90%.'
console.log(output);  // I like the song.
                      // I gave it a score of 90%.
````

# JS String Methods (w3schools)
- properties are used by:
`stringname.property`
- methods are used by:
`stringname.method()`
- strings are **immutable;** they cannot be changed, only replaced. 
- therefore all string methods **return a new string** 

## String Length Property
- use `length` property to return length of string

````
let txt = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
let length = txt.length;
````

## Extracting String Parts
3 methods for doing so:
1. `slice(start, end)`
2. `substring(start, end)`
3. `substr(start, length)`

- slice() and substring() are identical. specify start and end length. substring() treats negative values as 0 however
- JS is 0th-indexed
- substr() specifies start and length of extracted part instead of end

## Replacing String Content
- replace(specified, replacer) method replaces specified value in a string with another value 

- does not change string it is called on
- used to return a new string (declare new string, then assign with replace())
- replaces **only the first match**
- case sensitive matching (`/specified/i` insensitive flag = case-insensitive)
- global match flag /g replaces all matches in string--> `/specified/g` 

## Upper and Lower Case Conversions
- toUpperCase() and toLowerCase()

## Padding and Trim
1. trim() method removes whitespace from both sides of string
2. padStart() and padEnd() add padding to beginning or end of string

## Extracting String Characters
1. charAt(position) - returns character at specified position in string
2. charCodeAt(position) - returns Unicode of character at specified position in string
3. Property Access (with []) - string[position] accessing character at position

Property access:
- makes strings look like arrays (they arent)
- [] returns undefined if no char is found, charAt() returns empty string
- read-only. cannot replace/insert character at specified position

## Converting String --> Array
- dont using `split()` method.
- split("delimiter") converts string to array, using character delimiter to split string into different indices
````
text.split(",")    // Split on commas
text.split(" ")    // Split on spaces
text.split("|")    // Split on pipe
````
- not specifying delimiter will mean the returned array will contain the whole string in the first index [0].
- if delimiter is "", returned array will be array of single characters.

# List of String Methods 
### Found [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String).