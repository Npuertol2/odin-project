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

done by using:
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

# Conditionals

# Comparisons

## String Comparison

````
alert( 'Z' > 'A' ); // true
alert( 'Glow' > 'Glee' ); // true
alert( 'Bee' > 'Be' ); // true
````
- iterate through strings being compared
- if letters are same, go to next char
- if letter is lexographically greater/less, then it is true
- repeat until end of string
- strings of same length are equal,
- otherwise, longer string is greater
- Unicode Order (a > A because it has a greater index in Unicode internal encoding table)

## Comparison of Different Types
- JS converts string values to numbers when being compared 
`alert( '2' > 1 ); // true, string '2' becomes a number 2`
- true is equal to one while false is equal to 0
````
alert( true == 1 ); // true
alert( false == 0 ); // true
````

## Strict Equality
- regular equality check `==` cannot differentiate:
  - 0 from false 
  - empty string from false 
- this happens since **different type operands** are converted to numbers by the equality property.
- **strict equality** checks equality without type conversion 
  - if `a` and `b` are **different types**, `===` returns **false** 

## Comparison with null and undefined
- strict equality returns false since they are **different type**
- non-strict check shows that they **equal each other** but no any other value
- null and undefined are converted to numbers for other math comparisons
  - null = 0
  - undefiend = NaN

### null vs 0
- Because == does not convert null to 0, it will return strange result as seen below
````
alert( null > 0 );  // (1) false
alert( null == 0 ); // (2) false
alert( null >= 0 ); // (3) true
````

### undefined comparisons
- for comparisons other than equality, **undefined converts to NaN**
- NaN (not a number) returns **false for all comparisons**

# Conditionals (w3 schools)
1. `if` statements execute code block if condition is true
2. `else` statements execute code block if all conditions before it are false
3. `if else` statements execute code block if condition before it is false
4. `switch` statements are different format to conditionals, useful if there are more than 3 conditions to test for.
````
if (time < 10) {
  greeting = "Good morning";
} else if (time < 20) {
  greeting = "Good day";
} else {
  greeting = "Good evening";
}
````

# Logical Operators (JS fundamentals)

## || (OR)
- OR manipualtes boolean values only
- if any of the arguments are `true`, it returns `true`
- used in conditionals to test if **any** of the given conditions are **true**
````
alert( true || true );   // true
alert( false || true );  // true
alert( true || false );  // true
alert( false || false ); // false
````
- converts non boolean values to boolean values
  - 1 = true
  - 0 = false

### OR "||" finds the first truthy value
- OR works by:
  - evaluating from left to right
  - converts each operand to boolean. if result = `true`, it returns the **original value** of that operand
  - if all operands have been evaluated (all were false), returns **the last operand**

- Some uses include:
  1. getting first truthy value from list of variables/expressions
  ````
  let firstName = "";
  let lastName = "";
  let nickName = "SuperCoder";

  alert( firstName || lastName || nickName || "Anonymous"); // SuperCoder
  ````
  2. short-circuit evaluation
    - OR processes its argument until first truthy value
    - does not touch other part of argument
    - can be used with variable assignments / function calls in argument
    - people use this feature to execuite commands **only** if condition on the left part is falsy

## && (AND)
- classically, AND returns `true` if **both operands** are truthy

````
alert( true && true );   // true
alert( false && true );  // false
alert( true && false );  // false
alert( false && false ); // false
````

### AND "&&" finds first falsy value
- similar process as OR but instead of returning the first truthy value, it will return the first **falsy** value. 
- keeps going through each operand until it finds a false one
- if it goes through all operands, it returns the last one regardless of being false/true
- AND is higher precedence than OR 

## ! (NOT)
- accepts a single argument in front of it and does the following:
  - converts operand to boolean type: true/false
  - returns the inverse value of conversion

- double NOT `!!` is sometimes used for **value-to-boolean** conversion.
  - first `!` converts value to boolean and returns inverse
  - second `!` inverses it again

- ! is **highest** of all precedence of all logical operators
- ! > && > ||

````
alert( !true ); // false
alert( !0 ); // true
````

## Ternary Operator
- tests condition and returns one value/exoression if it is true, and another if it is false

````
( condition ) ? run this code : run this code instead

let greeting = ( isBirthday ) ? 'Happy birthday Mrs. Smith — we hope you have a great day!' : 'Good morning Mrs. Smith.';
````

### Multiple '?'
````
let age = prompt('age?', 18);

let message = (age < 3) ? 'Hi, baby!' :
  (age < 18) ? 'Hello!' :
  (age < 100) ? 'Greetings!' :
  'What an unusual age!';

alert( message );
````
````
let message = (login == 'Employee') ? 'Hello' : (login == 'Director') ? 'Greetings' : (login == '') ? 'No login' : '';
````


# Switch statements

### Example Switch Statement
````
switch (expression) {
	case x:
		// execute case x code block
		break;
	case y:
		// execute case y code block
		break;
	default:
		// execute default code block
}
````

### Switch Ranges
````
// Set the student's grade
const grade = 87;

switch (true) {
	// If score is 90 or greater
	case grade >= 90:
		console.log("A");
		break;
	// If score is 80 or greater
	case grade >= 80:
		console.log("B");
		break;
	// If score is 70 or greater
	case grade >= 70:
		console.log("C");
		break;
	// If score is 60 or greater
	case grade >= 60:
		console.log("D");
		break;
	// Anything 59 or below is failing
	default:
		console.log("F");
}
````
### Multiple Cases
````
// Get number corresponding to the current month, with 0 being January and 11 being December
const month = new Date().getMonth();

switch (month) {
	// January, February, March
	case 0:
	case 1:
	case 2:
		console.log("Winter");
		break;
	// April, May, June
	case 3:
	case 4:
	case 5:
		console.log("Spring");
		break;
	// July, August, September
	case 6:
	case 7:
	case 8:
		console.log("Summer");
		break;
	// October, November, December
	case 9:
	case 10:
	case 11:
		console.log("Autumn");
		break;
	default:
		console.log("Something went wrong.");
}
````

# Knowledge Check
- What are the eight data types in JavaScript?
- Which data type is NOT primitive?
- What is the relationship between null and undefined?
- What is the difference between single, double, and backtick quotes for strings?
- What is the term for embedding variables/expressions in a string?
- Which type of quote lets you embed variables/expressions in a string?
- How do you embed variables/expressions in a string?
- How do you escape characters in a string?
- What is the difference between the slice/substring/substr string methods?
- What are the three logical operators and what do they stand for?
- What are the comparison operators?
- What are truthy and falsy values?
- What are the falsy values in JavaScript?
- What are conditionals?
- What is the syntax for an if/else conditional?
- What is the syntax for a switch statement?
- What is the syntax for a ternary operator?
- What is nesting?