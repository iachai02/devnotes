# React Documentation Key Features

## Creating and nesting components

- react apps are made out of components
- `component`: piece of the UI that has its own logic and appearance

- Example

```JavaScript
function myButton() {
    return (
        <button>I'm a button</button>
    )
}

export default function MyApp() {
    return(
        <h1>Welcome to my App</h1>
        <MyButton />
    )
}
```

- `export default`: specify the main component in the file

## Adding Styles

- `className`: attribute that adds a class to an element

## Conditional Rendering

- Examples to conditionally render:
```Javascript
<div>
    {isLoggedIn ? (
        <AdminPanel />
    ) : (
        <LoginForm />
    )}
</div>

<div>
    {isLoggedIn && <AdminPanel />}
</div>
```

## Responding to events

- Example:
```Javascript
function MyButton() {
    function handleClick() {
        alert('You clicked me!');
    }

    return (
        <button onClick={handleClick}>
            Click me
        </button>
    );
}
```
- the `handleClick` in `onClick=` has no parentheses because you only need to pass it down. React will call your even handler when the user clicks the button

## Updating the screen

- `useState`: want your component to "remember" some information and display it
- `State variable`: `const [count, setCount] = useState(0);`
    - count: the current state
    - setCount: function that lets you update it

## Using Hooks

- functions starting with `use` are called Hooks
- you can write your own Hooks by combining the existing ones

## Sharing data between components

- Example:
```javascript
export default function MyApp() {
    const [count, setCount] = useState(0);

    function handleClick() {
        setCount(count + 1);
    }

    return (
        <div>
            <h1>Counters that update together</h1>
            <MyButton count={count} onClick={handleClick} />
            <MyButton count={count} onClick={handleClick} />
        </div>
    );
}
```
- information you pass down like `count` and `handleClick` are called props