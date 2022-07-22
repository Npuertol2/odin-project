# Fundamentals Part 1
Part 1 goes over:
 1. runing JS code, 
 2. variables, 
 3. and numbers.

## JS Functions learned:
1. console.log() -- print statement in browser console
2. let / var keyword -- assign variables 
3. alert() -- send alert banner with statement to webpage

## Running JS Code
Can be done directly through HTML or an external script to a .js file.

### Directly in HTML
1. In body element within <script></script> element
2. Add JS function or declaration
3. through HTML file in browser
4. Inspect element to use browser console --> console tab displays JS

### External Script
1. In script element
2. <script src="jsfile.js></script>`

## Variables
- named storage for data
- use **let** keyword to create variable
- **NOTE:** variable should only be declared once. Repeated declaration of same variable is an error.

### Different Types of Variable Declaration
```` 
// 1. variable declaration then assignment
let message;

message = 'Hello';

// 2. single line declaration + assignment (most common)
let message = 'Hello!';

// 3. multiple variables in one line
let user = 'John', age = 25, message = 'Hello';

// 4. multiline variant (per line)
let user = 'John';
let age = 25;
let message = 'Hello';

// 5. multiline style
let user = 'John',
  age = 25,
  message = 'Hello';
````

#### **var** vs **let**
- var keyword is *almost* the same as let
- "old-school" way
- will be discussed later

#### JS Variables are mutable + can be copied
- A variable can be changed as many times as we want
````
let message;

message = 'Hello!';

message = 'World!'; // value changed

alert(message);
````
- A variable can be assigned to another to copy one's data

````
let hello = 'Hello world!';

let message;

// copy 'Hello world' from hello into message
message = hello;

// now two variables hold the same data
alert(hello); // Hello world!
alert(message); // Hello world!
````

### Variable Naming
limitations on var names:
- name **MUST** contain only letters, digits, or symbols `$` and `$`.
- first character **must not be a digit**.
- Case matters (apple != APPLE)
- Non-Latin letters are allowed, but not recommended
- reserved names (let, class, return, function, etc.). list [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#keywords)
- make sure to declare variable first, then assign value

### Constants
- constant / unchanged / immutable variable use `const` isntead of `let`
`const myBirthday = '18.04.1982';`

#### Uppercase constants
- common practice to use constants as aliases for **difficult-to-remember** values known prior to execution

- such constants are made using capital letters and underscores
- examples include constants for colors and their hexadecimal values