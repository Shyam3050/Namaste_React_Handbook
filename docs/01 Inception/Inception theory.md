---
sidebar_position: 1
---

## Q: What is `Emmet`?

A: `Emmet` is the essential toolkit for web-developers. It allows you to `type shortcuts` that are then expanded into full pieces of code for writing `HTML and CSS`, based on an abbreviation structure most developers already use that expands into full-fledged HTML markup and CSS rules.

## Q: Difference between a `Library and Framework`?

A: A `library` is a collection of packages that perform specific operations whereas a `framework` contains the basic flow and architecture of an application. The major difference between them is the complexity. Libraries contain a number of methods that a developer can just call whenever they write code. React js is library and Angular is Framework. we can use React for small portion of our application.
The `framework` provides the flow of a software application and tells the developer what it needs and calls the code provided by the developer as required.

## Q: How to bring React into our Project & What is the way to get React?

A: we can use React in our project

- via CDN links
- npm registery package

via CDN links We just put the CDN links in our HTML file after that we use react code.

#### NOTE: Order of React files mater before import react we can't use it.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <div id="root"></div>

    <script
      crossorigin
      src="https://unpkg.com/react@18/umd/react.development.js"
    ></script>
    <script
      crossorigin
      src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"
    ></script>
    <!-- React code start -->
    <script>
      // define root for react
      const root = ReactDOM.createRoot(document.getElementById(root));
      // create react element
      const heading = React.createElement("h1", {}, "hello world");

      root.render(heading);
      // before insert react library we can't access React or ReactDOM object.
    </script>
  </body>
</html>
```

we can use react packages from npm.
npm install react react-dom

## Q why do we need both React and React Dom two libraries for devloping the react projects?

A: react library is the core of React ecosystem where the core react algorithm is written concepts like reconciliation, diffing algorithm and React Fibre thing there.
where React DOM is used by React to modify the actual DOM (browser DOM) with the help of React DOM.

## Q Why doesn't React organization can't bundle react and react-dom together?

A: React doesn't only work on browsers. It also works on a mobile device, smart watch etc. where React libray is core. For the browser we need React DOM Other devices have different DOMs so we can't merge React and React-DOM.

## Q Create and render the React element using core React & explain it?

A:
from .html file

```html
<div id="root"></div>
```

```js
const heading = React.createElement("h1", { id: "heading" }, "this is heading");
const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(heading);
```

output:

```html
<div id="root">
  <h1 id="heading">this is heading</h1>
</div>
```

React gives us a React object it has createElement() method.
This method needs three arguments.

- first one for html tags like h1, h2, div, p etc
- for set the attributes like {id: "idname", type : "button"} is same as

```html
<Tagname id="idname" type="button"> </Tagname>
```

- Third argument is children. which render inside the html element.
  > see the above example for better understand.

createRoot() lets you create a root to display React components inside a browser DOM node.

> Note: React.createElement() returns a object and ReactDOM.createRoot() also return object.

## Q: what happen when we do root.render(<App/>)?

A: It replace the root child with react element. (NOTE: not appended);

## Q: Is React library or Framework?

A: React is a library.

## Q: Create Nested element in React?

A:

```js
const parent = React.createElement(
  "div",
  { id: "parent" },
  React.createElement("h1", { id: "child" }, "this is heading")
);
```

so output in html will be

```html
<div id="parent">
  <h1 id="child">this is heading</h1>
</div>
```

## Q Create sibling element is React?

A: For sibling element we put elements in [];

```js
const parent = React.createElement("div", { id: "parent" }, [
  React.createElement("p", { id: "child1" }, "child1"),
  React.createElement("p", { id: "child2" }, "child2"),
]);
```

output

```html
<div id="parent">
  <p id="child1">child1</p>
  <p id="child2">child2</p>
</div>
```

## Q: What is difference between `react.development.js` and `react.production.js` files via `CDN`?

A: Development is the stage of an application before it's made public while production is the term used for the same application when it's made public. Development build is several times (maybe 3-5x) slower than the production build. Production code is the minified and optimized code.

## Q: what is modules in javascript?

A:
JavaScript modules allow you to break up your code into separate files.

> This makes it easier to maintain a code-base.
> Modules are imported from external files with the import statement.
> Modules also rely on type="module" in the `<script>` tag.

## Q: what is CDN?

A: A content delivery network (CDN) is a geographically distributed group of servers that caches content close to end users. A CDN allows for the quick transfer of assets needed for loading Internet content, including HTML pages, JavaScript files, stylesheets, images, and videos.
The popularity of CDN services continues to grow, and today the majority of web traffic is served through CDNs, including traffic from major sites like Facebook, Netflix, and Amazon

## Q: why we use CDN?

A:

- Improving website load times
- Reducing bandwidth costs
- Increasing content availability and redundancy
- Improving website security

## what is cross-origin?

A:
updating soon....

## async vs defer?

A: updating soon....
