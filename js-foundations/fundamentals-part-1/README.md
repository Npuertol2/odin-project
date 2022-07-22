# Fundamentals Part 1
Part 1 goes over:
 1. runing JS code, 
 2. variables, 
 3. and numbers.

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

