# React ⚛💙
### ✅ Also known as React.js/ React.JS
🌟 **Free & Open-Source JavaScript Library for building user interfaces (UIs).**

➡️ React is **Created by Meta (Facebook)** & is now maintained by Meta & community of developers.

* HTML/CSS/JS code refreshes the whole page unexpectedly upon interaction (like clicking a button, submitting a form, etc.)
### React Features:
* React is used to build *SPAs (Single Page Applications)*
* Creates *reusable UI components*
* Develops dynamic, fast & scalable front end applications.
* ReactJS uses a Virtual DOM mechanism to efficiently update the HTML DOM.
* Faster Navigation (No full page reloads)
* Allows writing HTML-like syntax inside JavaScript through JSX.
* Data flows in a single direction (parent → child).
* With React Native, the same concepts can be used to build mobile apps for Android and iOS.
* Huge ecosystem of libraries, tools, and community support.

### 👉 ReactJS uses a *Virtual DOM* mechanism to efficiently update the *HTML DOM.* 
Instead of reloading the entire DOM, the virtual DOM updates only the specific elements that have changed, resulting in faster performance.

### 👨‍💻 React follows a *Component-Driven Architecture*
The user interface is built by composing independent, reusable pieces called components. Each component manages its own logic and rendering, making development more modular, scalable, and easier to maintain.

**💡 A component is a reusable piece of code that represents a specific part of the user interface (UI).**

**React Element :** An object that describes the properties of an actual DOM node which will be created by React.

🌟 It contains information (like `type`, `props`, and `children`) about the actual DOM node that React will create and manage.

Simple Structure of a React Elements:
```
{
  type: "button",
  props: {
    className: "btn",
    children: "Click Me"
  }
}
```
📘 Explanation:
* `type` → The type of DOM element (e.g., "div", "button", etc.)
* `props` → The attributes or properties passed to the element
* `children` → The inner content or nested elements (optional)