---
sidebar_position: 1
---

## Q: What is useEffect() Hook Explain it?

A: The useEffect hook allows you to perforom side effects in your components. It need two argument

- a callback function
- [ ] dependency array (optional)

The callback function is called after renderd the component. <br>
If there is no dependency array useEffect is called every render.
<br>
If dependency array is empty [ ] then useEffect called only once. Even component render useEffect not called.
<br>
If anything in dependency array [fullName] element is changed then useEffect is called.
<br>
NOTE: If there are any state changes component is rendered if useEffect has no dependency array it's only rendered after the component is rendered.

## Q: What is best practice for useState() hook?

A:

- Always use useState() inside the component.
- It is used to create local state variable inside your functional component.
- Try to call the the Hooks on the top of component.
- Don't create state variable inside the if-else, for-loop and nested functions.

## Q: Create Routing using React-router-dom?

A: install the react-router-dom package from NPM

```js
 npm install react-router-dom
```

import the createBrowserRouter() from react-router-dom and config the routing.
<br>
see the below code:

```js
import { createBrowserRouter } from "react-router-dom";

const routerConfig = createBrowserRouter([
  {
    path: "/",
    element: <AppLayout />,
    errorElement: <Error />,
  },
  {
    path: "/about",
    element: <About />,
  },
  {
    path: "/contact",
    element: <Contact />,
  },
]);
```

```js
we successfully created the router config we also need to provide to our app so react-router-dom has

<RouterProvider router={routerConfig} /> component
```

```js
import { RouterProvider } from "react-router-dom";

//we can provide like this
ReactDOM.createRoot(document.getElementById("root")).render(
  <RouterProvider router={routerConfig} />
);
// OR
// Wrap it with root component
<RouterProvider router={routerConfig}>
  <App />
</RouterProvider>;
```

## Q: Create children Routing using React-router-dom?

A:

```js
import { RouterProvider, createBrowserRouter } from "react-router-dom";

const routerConfig = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    children: [
      {
        path: "/",
        element: <Body />,
      },
    ],
  },
]);
ReactDOM.createRoot(document.getElementById("root")).render(
  <RouterProvider router={routerConfig} />
);

// on App.js fileimport { Outlet } from "react-router-dom";
import Header from "./components/Header";

function App() {
  return (
    <>
      <Header />
      <Outlet />
    </>
  );
}

export default App;
import { Outlet } from "react-router-dom";
import Header from "./components/Header";

function App() {
  return (
    <>
      <Header />
      <Outlet />
    </>
  );
}

export default App;
```

## Q: Explain types of routing in web application?

A:

- client side routing
- server side routing

server side routing:- we make a network call to server for every page.
<br>
client side routing:- During the first network call server sent all component file whenever routes changes client side library (React) load the component without sending any network call to server.
<br>
NOTE:- All SPA (single page application) uses client side routing.

## Q: Create dynamic Routing using React-router-dom?

A:

```js
const routerConfig = createBrowserRouter([
  {
    path: "/",
    element: <App />,
    children: [
      {
        path: "/",
        element: <Body />,
      },
      {
        path: "/restaurants/:resid",
        element: <RestroDetail />,
      },
    ],
  },
]);
// on RestroDetail component we access the dynamic route using useParams() hook
```
