# Javascript

## Javascript Basics

- `alert()`: creates a popup with text inside
- `element.innerHTML`: modifies the webpage

## Numbers and Math

```javascript
1 + 1 = 3
1 * 1 = 1
1 - 1 = 0
1 / 1 = 1
(1 + 1) * 3 = 6
```

- `Math.round()`: rounds the number to the nearest whole number

## Strings

- `"", ''`
- ` `${}` `: can you interpolation

## Variables

- can use `let` or `const` to declare variables

## Booleans and If-Statements

- `===`: used to compare two things
- `&&`: AND operator
- `||`: OR operator
- `?`: ternary operator

## Functions

- `function functionName(param1) {}`: creates a function

## Objects

```javascript
const obj = {
    name: 'socks',
    price: 1090,
    message, // shorthand property if both the property name and value are the same
    method () { // creates a method
        ...
    }
};
```

- `obj.property`: to access a property of the object
- `obj['property']`: another way to access the property of the object
- `delete obj.property`: deletes the property
- `JSON`: JavaScript Object Notation
  - similar to javascript object, with less features (need to use "" and also can't use functions)
  - can be understood by most programming languages
- `JSON.stringify(object)`: converts to JSON syntax
- `JSON.parse(json)`: converts JSON back to an object
- `const object2 = object1`: this is just copying a reference to object2
- when you are comparing two objects, you are comparing the references, not the values inside
- `const { property } = object`: destructuring; takes the property from object and saves it to a variable

## Document Object Model (DOM)

- `document.title`: changes the title of the html document
- `document.body.innerHTML`: will change the html inside the body element to whatever you assign it to
- `document.querySelector('htmlElement')`: access any html element
  - `document.querySelector('.className')`: accesses the element given the class name
- `document.innerText('htmlElement')`: will get only the text not the entire html element
- `element.value`: gets the value of the element

## HTML, CSS, and Javscript Together

- `element.classList.add('class')`: adds a new class to the element
- `element.classList.remove('class')`: removes a class from the element

## Arrays and Loops

- `array.splice(0, 1)`: removes from the array (removed the first index of the array)
- `array.push(variable)`: add a value to an array

## Advanced Functions

- `setTimeout(function, milliseconds)`: waits for x amount of milliseconds and then call the function
- `setInterval(function, milliseconds)`: waits for x amount of milliseconds and then continually calls the function
- `clearInterval(intervalId)`: clears an interval
  `.forEach(function(value){})`: allows to loop through the array - using `return` is the same thing as `continue` for this function
- `const arrowFunction = () => {}`: arrow function
- `element.addEventListener('click', function)`: adds an event to an element
- `element.removeEventListener('click', function)`: removes an event
- `array.filter((value, index) => { condition to filter })`: filters out values based on criterias in the condition
- `array.map((value, index) => {})`: creates a new array and whatever we return, will be added to the new array

## Modules

- Help organize code so that when using multiple files, you can confine the variables to each file
- helps avoid naming conflicts
- create a module:
  - create a file
  - don't load the file with `<script>`
- get a variable out of a file
  - add type="module" attribute to your script tag
  - `export const variableName`
  - `import {variableName (optional but can add "as diffVariableName")} from 'filePath'`
