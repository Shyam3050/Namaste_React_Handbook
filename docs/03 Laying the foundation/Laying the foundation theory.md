---
sidebar_position: 1
---

## Q: What is JSX? Explain it?

A: Jsx is html like syntax is used to write html like syntax element in javascript.

> note: Jsx is not html both are different.
> jsx is html like syntax

- Jsx code doesn't understand the js engine.
- jsx not standard Ecmascript code.
- Even React or React-DOM doesn't understand the JSX code.

```js
root.render(<h1> this is heading </h1>);
// it cause error because it expect object which is React Element not jsx element.
```

so we need to change the JSX code into Javascript code.
Basically we have Babel(library) which converts JSX into javascript code.

> bundlers already have Babel in it.

```js
const myElement = <h1>I Love JSX!</h1>; // Babel converts this JSX into React Element which is an object.
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(myElement); // then render will understand the myElement.
```

## Q: Superpowers of JSX?

- we can write html like element in js.
- we can write javascript Expression.

```js
function greeting(user) {
  const date = new Date();
  //JSX
  return (
    <h1>
      {user}, How are you!!! @{date.getFullYear()}
    </h1>
  );
}
```

## Q: `{TitleComponent}` vs `{<TitleComponent/>}` vs `{<TitleComponent></TitleComponent>}` in `JSX`?

A: The Difference is stated below:

### `{TitleComponent}`

This value describes the `TitleComponent` as a javascript expression or a variable.
The `{}` can embed a javascript expression or a variable inside it.

```js
function Intro() {
  const titleComponent = "hello";
  return <h1>{titleComponent}</h1>;
}
```

### `<TitleComponent>{"some child code"}</TitleComponent>`

it is used when we need child element inside it.
here we have`{"some child code"}` so we need to wrap it inside the component.

### `<TitleComponent/>`

This value represents a Component that is basically returning Some JSX value. In simple terms `TitleComponent` a function that is returning a JSX value.
If there are no child components inside, we can use {< />}.

## Q: What makes React code Readable?

A: Your React code is readable because JSX make it readable.

```js
// with jsx
const Title = () => {
  return (
    <div>
      <h1>this is heading</h1>
    </div>
  );
};

// using with out jsx
const Title = () => {
  return React.createElement(
    "div",
    {},
    React.createElement("h1", {}, "this is heading")
  );
}; // for complex code it looks more complex understand.
```

> jsx makes developer experience better.

## Q: What is Functional Component?

A: It is a javascript function that returns some JSX code. Before it executes Babel compiles the returned JSX code and gives the normal javascript function.

> because JS engine or React doesn't understand JSX code so Babel convert Jsx into javascript code.

## Q: `<Title />` is is same as `Title()`?

A: yes We can call Functional component as a normal functional call. End of the day React functional Component is a normal javascript function.

## Q: What is Component composition?

A: Compose two components one and other

```js
const Title = () => {
  return <h1>This is Title</h1>;
};

const Heading = () => {
  return (
    <div>
      <Title />
    </div>
  );
};
```
