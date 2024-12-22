# Chapter - 03 - Laying The Foundation

## Theory Assignment Solutions

### Q: What is JSX?
A: JSX stands for `JavaScript XML`. It allows developers to write HTML-like code in JavaScript without using `createElement` in React, which can make React code more confusing and inefficient. JSX is not part of React itself but makes it easier to add HTML to React. JSX converts HTML code into JavaScript code that React can understand and render in the DOM. React developers prefer the conciseness of JSX.

Here's a simple example of JSX:
```javascript
const element = <h1>Hello, JSX!</h1>;
```
In the above code, it looks like HTML, but it's JSX. When this code is transpiled, it turns into JavaScript code that creates a React element, which can be rendered in a React application.

---

### Q: Rules of JSX
A: **1. Return a single root element** - To return multiple elements from a component, wrap them with a single parent tag. For instance, we can use a `<div>`:
```javascript
<div>
  <h1>Hedy Lamarr's Todos</h1>
  <img
    src="https://i.imgur.com/yXOvdOSs.jpg"
    alt="Hedy Lamarr"
    className="photo"
  />
  <ul>
    ...
  </ul>
</div>
```
If you don’t want to add an extra `<div>` to your markup, you can write `<>` and `</>` instead:
```javascript
<>
  <h1>Hedy Lamarr's Todos</h1>
  <img
    src="https://i.imgur.com/yXOvdOSs.jpg"
    alt="Hedy Lamarr"
    className="photo"
  />
  <ul>
    ...
  </ul>
</>
```
This empty tag is called a **Fragment**. Fragments let you group things without leaving any trace in the browser HTML tree.

**2. Close all the tags** - JSX requires tags to be explicitly closed. Self-closing tags like `<img>` must become `<img />`, and wrapping tags like `<li>` must be written as `<li>oranges</li>`.
```javascript
<>
  <img
    src="https://i.imgur.com/yXOvdOSs.jpg"
    alt="Hedy Lamarr"
    className="photo"
  />
  <ul>
    <li>Invent new traffic lights</li>
    <li>Rehearse a movie scene</li>
    <li>Improve the spectrum technology</li>
  </ul>
</>
```

---

### Q: Superpowers of JSX
A:
- **Integration of HTML-like Syntax** - JSX allows us to write code that looks like HTML in JavaScript, making it easy for developers to create user interfaces.

- **Component-Based Structure** - JSX is especially powerful when used with libraries like React. It enables us to create reusable UI components, making the code more modular and maintainable.

- **Dynamic Data Binding** - We can embed JavaScript expressions inside JSX using curly braces, allowing us to include and manipulate dynamic data within user interfaces. JSX is easy to maintain and debug.

---

### Q: Role of the type attribute in a script tag? What options can I use there?
A: The `type` attribute in a `<script>` tag specifies the media type of the script content. It tells the browser how to interpret the script. Some commonly used values include:

- **Omitted or Empty String**: If the type attribute is omitted or set to an empty string (`type=""`), the browser assumes the default JavaScript type, which is `text/javascript`. This is the most commonly used type for JavaScript and is supported by all modern browsers.
  ```html
  <script>
    // JavaScript code here
  </script>
  ```

- **text/javascript (Deprecated)**: While it used to be the default and widely used, specifying `type="text/javascript"` is no longer necessary in modern web development. Browsers assume the script is JavaScript by default. You can still use it for compatibility reasons, but it's not required.
  ```html
  <script type="text/javascript">
    // JavaScript code here
  </script>
  ```

- **module**: When `type="module"` is specified, the script is treated as an ECMAScript module. This value tells the browser that the script is a module that can import or export other files or modules.
  ```html
  <script type="module">
    // JavaScript module code here
  </script>
  ```

- **text/babel**: This value indicates that the script is of Babel type and requires the Babel JavaScript compiler to transpile JSX code.

- **text/typescript**: The script is written in TypeScript.

---

### Q: `{TitleComponent}` vs `{<TitleComponent/>}` vs `{<TitleComponent></TitleComponent>}` in `JSX`
A:
- **`{TitleComponent}`** - This expression is used when we want to embed a component as a JavaScript expression or a variable.
  ```javascript
  const TitleComponent = <h1>Hello, JSX!</h1>;

  const App = () => {
      return (
          <div>
              {TitleComponent}
          </div>
      );
  };
  ```

- **`{<TitleComponent/>}`** - This expression creates and renders an instance of the `TitleComponent` component. It's the most common way to use a component in JSX when we want to render the component as part of the UI.
  ```javascript
  const TitleComponent = () => <h1>Hello, JSX!</h1>;

  const App = () => {
      return (
          <div>
              <TitleComponent />
          </div>
      );
  };
  ```

- **`{<TitleComponent></TitleComponent>}`** - This is essentially the same as `{<TitleComponent/>}` in most cases. Both create and render an instance of the `TitleComponent` component. The explicit use of opening and closing tags might be used in situations where we want to include child elements within the `TitleComponent`.
  ```javascript
  <TitleComponent>
      <Header />
      <MainContainer />
      <SecondContainer />
  </TitleComponent>
  ```

