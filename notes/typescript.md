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

- you can make a parameter optional by adding a question mark at the end or give it a default value
  - `taxYear: number?` or `taxYear = 2022`

## Objects

```typescript
let employee: {
  readonly id: number;
  name: string;
} = { id: 1, name: "Mosh" };
```

## Advanced Types

```typescript
type Employee = {
  readonly id: number;
  name: string;
  retire: (date: Date) => void;
};
```

## Union Types

```typescript
function kgToLbs(weight: number | string): number {
  // Narrowing
  if (typeof weight === "number") {
    return weight * 2.2;
  } else {
    return parseInt(weight) * 2.2;
  }
}

kgToLbs(10);
kgToLbs("10kg");
```

## Intersection Types

```typescript
type Draggable = {
  drag: () => void;
};

type Resizable = {
  resize: () => void;
};

type UIWidget = Draggable & Resizable;

let textBox: UIWidget = {
  drag: () => {},
  resize: () => {},
};
```

## Literal Types

```typescript
type Quantity = 50 | 100;
let quantity: Quantity = 100;

type Metric = "cm" | "inch";
```

## Nullable Types

```typescript
function greet(name: string | null | undefined) {
  if (name) console.log(name.toUpperCase());
  else console.log("Hola!");
}

greet(null);
```

## Optional Chaining

```typescript
type Customer = {
  birthday: Date;
};

function getCustomer(id: number): Customer | null | undefined {
  return id === 0 ? null : { birthday: new Date() };
}

let customer = getCustomer(0);
// Optional property access operator
console.log(customer?.birthday);

// Optional element access operator
let log: any = null;
log?.("a");
```
