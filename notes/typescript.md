# TYPESCRIPT

## Introduction to Typescript

- checks for types at compilation instead of dynamically
- typescript is built on top of javascript
- benefits
  - static typing
  - code completion
  - refactoring
  - shorthand notations
  - medium/larger projects

## Built-in Types

- `any`
- `unknown`
- `never`
- `enum`
- `tuple`

## 'any' type

- you should avoid using `any` type whenever possible

## Arrays

- `let numbers: number[] = [1, 2, 3];`
  - can remove the `number[]` annotation because it will infer that the array is a number array

## Tuples

- `let user: [number, string, boolean, number] = [1, 'Mosh', true, 0];`

## Enums

- `enum Size { Small = 's', Medium = 'm', Larget = 'l' };`
  - used to list of related constants

## Functions

```typescript
function calculateTax(income: number): number {
  return income;
}
```
