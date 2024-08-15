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
    price: 1090
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