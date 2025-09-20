# ❓React Interview Questions 
### What are the feature of React?
* React is used to build *SPAs (Single Page Applications)*
* Creates *reusable UI components*
* ReactJS uses a Virtual DOM mechanism to efficiently update the HTML DOM.
* Faster Navigation (No full page reloads)
* Allows writing HTML-like syntax inside JavaScript through JSX.
* Data flows in a single direction (parent → child).
* With React Native, the same concepts can be used to build mobile apps for Android and iOS.
* Huge ecosystem of libraries, tools, and community support.

### What's the use of Babel?
Babel is a JavaScript transpiler, which is a specific type of compiler mainly used to convert modern JavaScript (ES6+ and beyond) code into backward-compatible JavaScript that can run in older browsers or environments.

* JSX Support: Converts JSX (used in React) into plain JavaScript that browsers can understand.

### Difference between Virtual DOM & Real DOM
| **Feature**      | **Real DOM**                                                             | **Virtual DOM**                                                                                                            |
| ---------------- | ------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| **Definition**   | The actual DOM (Document Object Model) rendered by the browser.          | A lightweight in-memory representation (copy) of the real DOM maintained by React.                                         |
| **Updates**      | Directly updates the UI.                                                 | Updates happen in the virtual DOM first, then React compares (diffing) and updates only the changed parts in the real DOM. |
| **Performance**  | Slower when frequent updates occur (manipulating real DOM is expensive). | Faster updates due to efficient diffing and batching of changes.                                                           |
| **Re-rendering** | Entire UI or large parts may re-render even for small changes.           | Only the changed nodes are re-rendered in the real DOM after comparison.                                                   |
| **Memory Usage** | Takes more memory and resources.                                         | Lightweight, stored in memory only.                                                                                        |
| **Example**      | `document.getElementById()` directly modifies elements.                  | React internally creates a virtual DOM tree to update UI efficiently.                                                      |

### What are the Features of ES6?
* Let and Const - Block-scoped variables. let for mutable values, const for immutable values.

* Arrow Functions - Shorter function syntax. Lexically binds this (no need for .bind()).

* Template Literals - Use backticks (`) for string interpolation. Supports multi-line strings.

* Default Parameters - Set default values for function parameters directly.

* Destructuring Assignment - Extract values from arrays/objects into variables easily.

* Spread and Rest Operators (...) - Spread: Expand arrays/objects.
  
* Promises: Built-in support for asynchronous operations. Replaces complex callback patterns.

### Difference between Class Components & Functional Components in React?
| **Aspect**                          | **Class Components**                                                                 | **Functional Components**                                                 |
| ----------------------------------- | ------------------------------------------------------------------------------------ | ------------------------------------------------------------------------- |
| **Definition**                      | ES6 classes that extend `React.Component`.                                           | Plain JavaScript functions that return JSX.                               |
| **Syntax**                          | More verbose, use `class MyComponent extends React.Component`.                       | Simpler, just `function MyComponent() { return <JSX/> }`.                 |
| **State Management (Before Hooks)** | Can hold and manage state using `this.state` and `this.setState()`.                  | Initially stateless (until Hooks were introduced).                        |
| **Lifecycle Methods**               | Have built-in lifecycle methods like `componentDidMount`, `componentDidUpdate`, etc. | Lifecycle handled using Hooks like `useEffect()`.                         |
| **Hooks Support**                   | Not needed (state & lifecycle already built-in).                                     | Use Hooks (`useState`, `useEffect`, etc.) for state & lifecycle features. |
| **Performance**                     | Slightly heavier due to `this` binding and more boilerplate.                         | Lighter and faster because they’re just functions.                        |
| **‘this’ Keyword**                  | Must bind `this` to event handlers manually or use arrow functions.                  | No `this` keyword, easier to read & maintain.                             |
| **Recommended Usage**               | Older React apps (before Hooks).                                                     | Modern React apps (preferred approach today).                             |

### What's `useState`
`useState` is a React Hook that allows you to add state to functional components.

Syntax:
```
const [state, setState] = useState(initialValue);
```

`state` → current state value.

`setState` → function to update the state.

`initialValue` → starting value of the state.

Key Points:
* State is preserved between re-renders.
* Updating state with setState causes the component to re-render.
* You can store any type (string, number, array, object, etc.).
* State updates are asynchronous and batched.

### What's the difference between Controlled & Uncontrolled Components in React?
| **Aspect**          | **Controlled Component**                                               | **Uncontrolled Component**                                    |
| ------------------- | ---------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Definition**      | Form data is **handled by React state**.                               | Form data is **handled by the DOM** itself.                   |
| **Data Source**     | React state is the single source of truth.                             | The DOM (via refs) is the source of truth.                    |
| **Value Prop**      | Input value is bound to a state variable (`value={state}`).            | Input value is not bound to state; accessed only when needed. |
| **Change Handling** | Every change triggers an `onChange` event to update state.             | No `onChange` needed to update state continuously.            |
| **Accessing Value** | Directly from React state.                                             | Using `ref` or `document.getElementById()` to read value.     |
| **Example Usage**   | When you need validation, conditional disabling, or real-time updates. | When you just need the final value at submission time.        |

### What's Prop Drilling?
Prop drilling happens when you pass data (props) from a parent component to a deeply nested child component by passing it through multiple intermediate components that don’t actually need the data.

#### Why It Happens:
React only allows data to flow one way (top → down), so if a deeply nested component needs data, you often have to pass it through every component in the hierarchy.

Problem:
* Intermediate components become cluttered with props they don’t use.
* Code becomes harder to maintain.
* Changes to props can cause unnecessary re-renders.

Solutions to Avoid Prop Drilling:
* React Context API (most common)
* State Management Libraries (Redux, Zustand, Recoil, Jotai)
* Custom Hooks (if only logic is shared)