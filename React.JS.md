### 1. **Introduction to ReactJS**
ReactJS is a JavaScript library for building user interfaces, maintained by Facebook. It is declarative, component-based, and focuses on building reusable UI components.

#### Key Concepts:
- **React Virtual DOM**: React maintains a lightweight copy of the real DOM, allowing it to update only the parts of the UI that change, leading to improved performance.
- **JSX**: JavaScript XML is a syntax extension that looks like HTML and is used to define UI elements in React.

#### Installation and Setup:
1. Install Node.js and npm.
2. Create a React project using `create-react-app`:
   ```bash
   npx create-react-app my-app
   cd my-app
   npm start
   ```
3. The development server will start at `http://localhost:3000`.

#### Example:
```jsx
import React from 'react';
import ReactDOM from 'react-dom';

const App = () => <h1>Hello, React!</h1>;

ReactDOM.render(<App />, document.getElementById('root'));
```

---

### 2. **React Components**
Components are the building blocks of a React application. There are two main types:
1. **Class Components**: Use ES6 classes and have access to lifecycle methods.
2. **Functional Components**: Simple JavaScript functions that use hooks to manage state and lifecycle.

#### Example:
**Class Component:**
```jsx
import React, { Component } from 'react';

class Welcome extends Component {
  render() {
    return <h1>Welcome, {this.props.name}!</h1>;
  }
}
```

**Functional Component:**
```jsx
const Welcome = ({ name }) => <h1>Welcome, {name}!</h1>;
```

#### Lifecycle Methods:
Class components offer methods like `componentDidMount`, `shouldComponentUpdate`, and `componentWillUnmount`.

#### Hooks Introduction:
Hooks like `useState` and `useEffect` allow state management and side effects in functional components.
```jsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

---

### 3. **React State and Props**
- **State**: An object managed within a component.
- **Props**: Data passed from a parent component to a child.

#### Example:
```jsx
const Parent = () => <Child message="Hello from parent!" />;

const Child = ({ message }) => <p>{message}</p>;
```

#### State Management:
```jsx
const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

#### State Lifting:
State is lifted when a parent manages state for its children.
```jsx
const Parent = () => {
  const [value, setValue] = useState('');

  return <Child value={value} onChange={setValue} />;
};

const Child = ({ value, onChange }) => (
  <input value={value} onChange={(e) => onChange(e.target.value)} />
);
```

#### Prop Drilling:
Occurs when props are passed down through multiple components.
```jsx
const GrandParent = () => <Parent message="Hello!" />;

const Parent = ({ message }) => <Child message={message} />;

const Child = ({ message }) => <p>{message}</p>;
```

---

### 4. **Event Handling in React**
React uses synthetic events, which are wrappers around native DOM events for cross-browser compatibility.

#### Example:
**Functional Component Event:**
```jsx
const ClickButton = () => {
  const handleClick = () => alert('Button clicked!');
  
  return <button onClick={handleClick}>Click Me</button>;
};
```

**Class Component Event:**
```jsx
class ClickButton extends React.Component {
  handleClick = () => alert('Button clicked!');

  render() {
    return <button onClick={this.handleClick}>Click Me</button>;
  }
}
```

#### Binding Event Handlers:
For class components, event handlers are often bound in the constructor or as arrow functions:
```jsx
constructor() {
  super();
  this.handleClick = this.handleClick.bind(this);
}
```

---

### 5. **React Forms**
Forms in React can be **controlled** or **uncontrolled**:
- **Controlled Components**: Form elements are controlled by React state.
- **Uncontrolled Components**: Form data is handled directly by the DOM using `ref`.

#### Example:
**Controlled Form:**
```jsx
const Form = () => {
  const [input, setInput] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Submitted: ${input}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input value={input} onChange={(e) => setInput(e.target.value)} />
      <button type="submit">Submit</button>
    </form>
  );
};
```

**Uncontrolled Form:**
```jsx
import React, { useRef } from 'react';

const Form = () => {
  const inputRef = useRef();

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Submitted: ${inputRef.current.value}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input ref={inputRef} />
      <button type="submit">Submit</button>
    </form>
  );
};
```

#### Form Validation:
```jsx
const Form = () => {
  const [email, setEmail] = useState('');
  const [error, setError] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    if (!email.includes('@')) {
      setError('Invalid email');
    } else {
      setError('');
      alert('Form submitted');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        value={email}
        onChange={(e) => setEmail(e.target.value)}
        placeholder="Email"
      />
      {error && <p style={{ color: 'red' }}>{error}</p>}
      <button type="submit">Submit</button>
    </form>
  );
};
```
### 6. **React Hooks**

Hooks are functions introduced in React 16.8 to manage state and lifecycle in functional components. Common hooks include:

#### 1. **useState**:
Manages state in functional components.
```jsx
const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
```

#### 2. **useEffect**:
Performs side effects like data fetching, subscriptions, or manually updating the DOM.  
- **Dependencies**: Controls when `useEffect` runs. An empty array (`[]`) runs it only on mount, while including variables re-runs it on their change.
- **Cleanup**: Used to clean up subscriptions or event listeners.
```jsx
useEffect(() => {
  const timer = setInterval(() => console.log('Interval running'), 1000);
  return () => clearInterval(timer); // Cleanup on unmount
}, []);
```

#### 3. **useContext**:
Accesses context values without prop drilling.
```jsx
const ThemeContext = React.createContext('light');

const ThemeDisplay = () => {
  const theme = useContext(ThemeContext);
  return <p>Current theme: {theme}</p>;
};
```

#### 4. **Custom Hooks**:
Reusable logic extracted into a custom hook.
```jsx
const useCounter = (initialValue = 0) => {
  const [count, setCount] = useState(initialValue);
  const increment = () => setCount((prev) => prev + 1);
  return { count, increment };
};

const Counter = () => {
  const { count, increment } = useCounter(10);
  return <button onClick={increment}>Count: {count}</button>;
};
```

---

### 7. **React Router**

React Router enables navigation in React apps.

#### Setup:
Install React Router:  
```bash
npm install react-router-dom
```

#### Basic Example:
```jsx
import { BrowserRouter, Route, Routes, Link } from 'react-router-dom';

const Home = () => <h1>Home</h1>;
const About = () => <h1>About</h1>;

const App = () => (
  <BrowserRouter>
    <nav>
      <Link to="/">Home</Link>
      <Link to="/about">About</Link>
    </nav>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  </BrowserRouter>
);
```

#### Nested Routes:
```jsx
const Dashboard = () => (
  <Routes>
    <Route path="overview" element={<h1>Overview</h1>} />
    <Route path="settings" element={<h1>Settings</h1>} />
  </Routes>
);
```

#### Dynamic Routing:
```jsx
const User = ({ id }) => <h1>User ID: {id}</h1>;

const App = () => (
  <Routes>
    <Route path="/user/:id" element={<User />} />
  </Routes>
);
```

#### Programmatic Navigation:
```jsx
import { useNavigate } from 'react-router-dom';

const NavigateButton = () => {
  const navigate = useNavigate();
  return <button onClick={() => navigate('/about')}>Go to About</button>;
};
```

---

### 8. **React Context API**

The Context API shares state globally across components without prop drilling.

#### Example:
```jsx
const ThemeContext = React.createContext();

const App = () => {
  const [theme, setTheme] = useState('light');
  return (
    <ThemeContext.Provider value={{ theme, setTheme }}>
      <Toolbar />
    </ThemeContext.Provider>
  );
};

const Toolbar = () => <ThemeSwitcher />;

const ThemeSwitcher = () => {
  const { theme, setTheme } = useContext(ThemeContext);
  return (
    <button onClick={() => setTheme(theme === 'light' ? 'dark' : 'light')}>
      Switch to {theme === 'light' ? 'dark' : 'light'} mode
    </button>
  );
};
```

---

### 9. **Styling in React**

React supports multiple styling approaches:

#### 1. **CSS Modules**:
Scoped styles to avoid class name collisions.
```css
/* styles.module.css */
.button {
  background-color: blue;
}
```
```jsx
import styles from './styles.module.css';

const App = () => <button className={styles.button}>Click Me</button>;
```

#### 2. **Styled-Components**:
CSS-in-JS approach using a library.
```bash
npm install styled-components
```
```jsx
import styled from 'styled-components';

const Button = styled.button`
  background-color: blue;
  color: white;
`;

const App = () => <Button>Click Me</Button>;
```

#### 3. **Inline Styles**:
Passing styles as JavaScript objects.
```jsx
const App = () => <div style={{ color: 'red' }}>Hello</div>;
```

#### 4. **CSS Frameworks**:
- **Material-UI**: Ready-made components.
  ```bash
  npm install @mui/material @emotion/react @emotion/styled
  ```
  ```jsx
  import { Button } from '@mui/material';

  const App = () => <Button variant="contained">Click Me</Button>;
  ```

- **TailwindCSS**: Utility-first CSS framework.
  ```bash
  npm install tailwindcss postcss autoprefixer
  ```
  ```jsx
  const App = () => <button className="bg-blue-500 text-white">Click Me</button>;
  ```

---

### 10. **State Management Libraries**

React state management libraries manage global state across components.

#### 1. **Redux**:
A predictable state container.
```bash
npm install redux react-redux
```
```jsx
import { createStore } from 'redux';
import { Provider, useSelector, useDispatch } from 'react-redux';

const reducer = (state = { count: 0 }, action) => {
  switch (action.type) {
    case 'INCREMENT':
      return { ...state, count: state.count + 1 };
    default:
      return state;
  }
};

const store = createStore(reducer);

const Counter = () => {
  const count = useSelector((state) => state.count);
  const dispatch = useDispatch();
  return (
    <button onClick={() => dispatch({ type: 'INCREMENT' })}>Count: {count}</button>
  );
};

const App = () => (
  <Provider store={store}>
    <Counter />
  </Provider>
);
```

#### 2. **Redux Toolkit**:
Simplifies Redux usage.
```bash
npm install @reduxjs/toolkit react-redux
```
```jsx
import { configureStore, createSlice } from '@reduxjs/toolkit';
import { Provider, useSelector, useDispatch } from 'react-redux';

const counterSlice = createSlice({
  name: 'counter',
  initialState: { count: 0 },
  reducers: {
    increment: (state) => {
      state.count += 1;
    },
  },
});

const store = configureStore({ reducer: counterSlice.reducer });

const Counter = () => {
  const count = useSelector((state) => state.count);
  const dispatch = useDispatch();
  return (
    <button onClick={() => dispatch(counterSlice.actions.increment())}>
      Count: {count}
    </button>
  );
};

const App = () => (
  <Provider store={store}>
    <Counter />
  </Provider>
);
```

#### 3. **MobX**:
Manages state using observables.
```bash
npm install mobx mobx-react-lite
```

#### 4. **Zustand**:
Simpler state management.
```bash
npm install zustand
```
```jsx
import create from 'zustand';

const useStore = create((set) => ({
  count: 0,
  increment: () => set((state) => ({ count: state.count + 1 })),
}));

const Counter = () => {
  const { count, increment } = useStore();
  return <button onClick={increment}>Count: {count}</button>;
};
```

### 11. **Performance Optimization**

React provides several tools and patterns to optimize performance:

#### 1. **React.memo**:
Wraps a functional component to prevent unnecessary re-renders when props haven't changed.
```jsx
const Child = React.memo(({ value }) => {
  console.log("Rendering Child");
  return <p>{value}</p>;
});

const Parent = () => {
  const [count, setCount] = useState(0);
  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <Child value="Hello" />
    </div>
  );
};
```

#### 2. **useMemo**:
Caches the result of expensive calculations based on dependencies.
```jsx
const ExpensiveCalculation = ({ num }) => {
  const result = useMemo(() => {
    console.log("Calculating...");
    return num ** 2;
  }, [num]);

  return <p>Result: {result}</p>;
};
```

#### 3. **useCallback**:
Memoizes a function reference to avoid re-creation on every render.
```jsx
const Button = React.memo(({ onClick }) => {
  console.log("Rendering Button");
  return <button onClick={onClick}>Click Me</button>;
});

const Parent = () => {
  const [count, setCount] = useState(0);
  const increment = useCallback(() => setCount((prev) => prev + 1), []);
  return (
    <div>
      <p>Count: {count}</p>
      <Button onClick={increment} />
    </div>
  );
};
```

#### 4. **Lazy Loading and Code Splitting**:
Split code into smaller chunks and load them on demand.
```jsx
const LazyComponent = React.lazy(() => import('./LazyComponent'));

const App = () => (
  <React.Suspense fallback={<p>Loading...</p>}>
    <LazyComponent />
  </React.Suspense>
);
```

---

### 12. **Higher-Order Components (HOCs)**

HOCs are functions that take a component and return a new component with additional functionality.

#### Example:
```jsx
const withLogging = (WrappedComponent) => (props) => {
  console.log("Component rendered with props:", props);
  return <WrappedComponent {...props} />;
};

const Button = ({ label }) => <button>{label}</button>;

const LoggingButton = withLogging(Button);
```

#### Alternatives:
- Hooks (`useEffect` for side effects, `useContext` for shared logic).
- Render props for more flexible composition.

---

### 13. **React Portals**

Portals allow rendering children outside the parent DOM hierarchy, often used for modals or tooltips.
```jsx
const Modal = ({ children }) =>
  ReactDOM.createPortal(children, document.getElementById("modal-root"));

const App = () => (
  <div>
    <h1>Main App</h1>
    <Modal>
      <p>This is a modal</p>
    </Modal>
  </div>
);
```

---

### 14. **Error Boundaries**

Error boundaries catch JavaScript errors in components and display fallback UI instead of crashing the app.

#### Example:
```jsx
class ErrorBoundary extends React.Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    console.error(error, info);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

const App = () => (
  <ErrorBoundary>
    <ProblematicComponent />
  </ErrorBoundary>
);
```

---

### 15. **React Fragments**

Fragments allow grouping of elements without adding extra nodes to the DOM.

#### Example:
```jsx
const App = () => (
  <>
    <h1>Title</h1>
    <p>Description</p>
  </>
);
```

---

### 16. **Testing React Applications**

#### 1. **Unit Testing with Jest**:
```bash
npm install jest
```
```jsx
test('adds 1 + 2 to equal 3', () => {
  expect(1 + 2).toBe(3);
});
```

#### 2. **React Testing Library**:
```bash
npm install @testing-library/react
```
```jsx
import { render, screen } from '@testing-library/react';
import App from './App';

test('renders hello message', () => {
  render(<App />);
  expect(screen.getByText(/hello/i)).toBeInTheDocument();
});
```

#### 3. **End-to-End Testing with Cypress**:
```bash
npm install cypress
```
```javascript
describe('My First Test', () => {
  it('Visits the app', () => {
    cy.visit('http://localhost:3000');
    cy.contains('Hello');
  });
});
```

---

### 17. **React Animations**

#### 1. **React Spring**:
```bash
npm install @react-spring/web
```
```jsx
import { useSpring, animated } from '@react-spring/web';

const App = () => {
  const styles = useSpring({ from: { opacity: 0 }, to: { opacity: 1 } });
  return <animated.div style={styles}>Hello</animated.div>;
};
```

#### 2. **Framer Motion**:
```bash
npm install framer-motion
```
```jsx
import { motion } from 'framer-motion';

const App = () => (
  <motion.div animate={{ x: 100 }}>Hello</motion.div>
);
```

---

### 18. **Integrating APIs in React**

#### Fetch API:
```jsx
useEffect(() => {
  fetch('https://api.example.com/data')
    .then((res) => res.json())
    .then((data) => console.log(data));
}, []);
```

#### Axios:
```bash
npm install axios
```
```jsx
import axios from 'axios';

useEffect(() => {
  axios.get('https://api.example.com/data').then((response) => console.log(response.data));
}, []);
```

---

### 19. **React Server Components**

React Server Components (RSC) allow server-rendered logic to send HTML directly to the client. They optimize performance by reducing JavaScript on the client.

#### Example (Next.js integration):
```jsx
// server.js
export default function Component() {
  return <h1>This is server-rendered</h1>;
}
```

---

### 20. **React and TypeScript**

TypeScript provides static typing for React applications.

#### Typing Props and State:
```tsx
type Props = { message: string };
const App: React.FC<Props> = ({ message }) => <h1>{message}</h1>;
```

#### Typing Hooks:
```tsx
const [count, setCount] = useState<number>(0);
```

### 21. **Next.js for React**

Next.js is a React framework for building server-side rendered (SSR) and static websites. 

#### Key Features:
- **SSR**: Renders pages on the server for better SEO and faster load times.
- **Static Site Generation (SSG)**: Pre-builds pages at compile time.
- **API Routes**: Serverless functions for backend logic.

#### Example: Basic Next.js App
```bash
npx create-next-app my-next-app
```

#### Pages:
Create a file `pages/index.js`:
```jsx
export default function Home() {
  return <h1>Welcome to Next.js!</h1>;
}
```

#### API Routes:
Create `pages/api/hello.js`:
```jsx
export default function handler(req, res) {
  res.status(200).json({ message: "Hello, API!" });
}
```

#### Static Site Generation (SSG):
```jsx
export async function getStaticProps() {
  return { props: { message: "Static Content" } };
}

export default function Home({ message }) {
  return <p>{message}</p>;
}
```

---

### 22. **React Native**

React Native is used to build mobile apps with React. It differs from ReactJS by rendering native components instead of HTML.

#### Example: Setting Up React Native
```bash
npx react-native init MyApp
```

#### Example App:
```jsx
import { View, Text, Button } from 'react-native';

export default function App() {
  return (
    <View>
      <Text>Hello, React Native!</Text>
      <Button title="Press Me" onPress={() => alert("Button Pressed!")} />
    </View>
  );
}
```

---

### 23. **Advanced Patterns in React**

#### 1. **Render Props**:
A technique where a function is passed as a prop to control rendering.
```jsx
const DataProvider = ({ render }) => {
  const data = { message: "Hello" };
  return render(data);
};

const App = () => (
  <DataProvider render={(data) => <p>{data.message}</p>} />
);
```

#### 2. **Compound Components**:
Enables components to work together with implicit relationships.
```jsx
const Tabs = ({ children }) => <div>{children}</div>;
Tabs.Tab = ({ title }) => <button>{title}</button>;

const App = () => (
  <Tabs>
    <Tabs.Tab title="Tab 1" />
    <Tabs.Tab title="Tab 2" />
  </Tabs>
);
```

#### 3. **Controlled vs. Uncontrolled Components**:
- **Controlled**: State is managed by React.
- **Uncontrolled**: State is managed by the DOM.
```jsx
// Controlled:
const ControlledInput = () => {
  const [value, setValue] = useState("");
  return <input value={value} onChange={(e) => setValue(e.target.value)} />;
};

// Uncontrolled:
const UncontrolledInput = () => {
  const inputRef = useRef();
  return <input ref={inputRef} />;
};
```

---

### 24. **Building Reusable Components**

Reusable components should be modular, flexible, and customizable.

#### Example: Button Component
```jsx
const Button = ({ label, onClick, style }) => (
  <button onClick={onClick} style={style}>
    {label}
  </button>
);

const App = () => (
  <Button label="Click Me" onClick={() => alert("Clicked!")} style={{ color: "blue" }} />
);
```

#### Creating a Component Library:
Use **Storybook** to document and test reusable components.

---

### 25. **React with GraphQL**

GraphQL is a query language for APIs. Apollo Client and Relay are popular tools for integration.

#### Example with Apollo Client:
```bash
npm install @apollo/client graphql
```
```jsx
import { ApolloClient, InMemoryCache, ApolloProvider, useQuery, gql } from "@apollo/client";

const client = new ApolloClient({
  uri: "https://graphql-pokemon2.vercel.app/",
  cache: new InMemoryCache(),
});

const GET_POKEMON = gql`
  query {
    pokemon(name: "Pikachu") {
      name
      image
    }
  }
`;

const Pokemon = () => {
  const { loading, error, data } = useQuery(GET_POKEMON);
  if (loading) return <p>Loading...</p>;
  if (error) return <p>Error: {error.message}</p>;
  return <img src={data.pokemon.image} alt={data.pokemon.name} />;
};

const App = () => (
  <ApolloProvider client={client}>
    <Pokemon />
  </ApolloProvider>
);
```

---

### 26. **Micro-Frontend Architecture**

Micro-frontends split a large app into smaller, independently deployable apps.

#### Example with Module Federation:
- **Host App** imports remote modules.
- Use tools like **Webpack Module Federation** or **Single SPA**.

---

### 27. **Deployment of React Applications**

#### 1. **Vercel**:
```bash
npx vercel
```

#### 2. **Netlify**:
Drag and drop the build folder or use CLI.

#### 3. **AWS Amplify**:
```bash
amplify publish
```

---

### 28. **React Concurrent Features**

Concurrent mode improves rendering performance. **Suspense** and **startTransition** are key features.

#### Example: Suspense for Data Fetching
```jsx
const resource = fetchData();

const App = () => (
  <React.Suspense fallback={<p>Loading...</p>}>
    <Data resource={resource} />
  </React.Suspense>
);
```

---

### **Why ReactJS? Features of ReactJS**

**ReactJS** is a popular JavaScript library for building user interfaces due to its simplicity, flexibility, and performance.  
#### Features:  
1. **Component-Based Architecture**: Build encapsulated components that manage their own state.  
2. **Virtual DOM**: Efficiently updates the DOM for better performance.  
3. **Declarative UI**: Makes code predictable and easy to debug.  
4. **Unidirectional Data Flow**: Data flows in a single direction, improving control.  
5. **React Hooks**: Manage state and side effects in functional components.  
6. **JSX**: Combines JavaScript and HTML for a cleaner syntax.  
7. **Rich Ecosystem**: Libraries like Redux, React Router, and more extend functionality.  

---

### **How to Create Custom Hooks in ReactJS and Its Purpose**

Custom hooks encapsulate reusable logic, making code cleaner and maintainable.  

#### Example:
```jsx
import { useState, useEffect } from "react";

const useFetch = (url) => {
  const [data, setData] = useState(null);

  useEffect(() => {
    fetch(url)
      .then((res) => res.json())
      .then((data) => setData(data));
  }, [url]);

  return data;
};

const App = () => {
  const data = useFetch("https://api.example.com/items");

  return <div>{data ? data.map((item) => <p key={item.id}>{item.name}</p>) : "Loading..."}</div>;
};
```

---

### **Hooks in ReactJS**

1. **State Hooks**: `useState`  
2. **Effect Hooks**: `useEffect`  
3. **Context Hooks**: `useContext`  
4. **Ref Hooks**: `useRef`  
5. **Callback Hooks**: `useCallback`  
6. **Memoization Hooks**: `useMemo`  
7. **Reducer Hooks**: `useReducer`  
8. **Custom Hooks**: User-defined hooks.  

---

### **Difference Between Function Component and Class Component**

| Feature                 | Function Component             | Class Component                 |
|-------------------------|-------------------------------|---------------------------------|
| Syntax                  | Functions                     | ES6 Classes                    |
| State Management        | `useState` hook               | `this.state`                   |
| Lifecycle Methods       | Hooks (`useEffect`, etc.)     | `componentDidMount`, etc.      |
| Performance             | Lightweight                   | Slightly heavier               |
| Boilerplate             | Less                          | More                           |

---

### **What is Higher Order Component (HOC)?**

A Higher Order Component (HOC) is a function that takes a component and returns a new component, enhancing functionality.  

#### Example:
```jsx
const withLogging = (WrappedComponent) => {
  return (props) => {
    console.log("Props:", props);
    return <WrappedComponent {...props} />;
  };
};

const Button = ({ label }) => <button>{label}</button>;

const EnhancedButton = withLogging(Button);

const App = () => <EnhancedButton label="Click Me" />;
```

---

### **What is Virtual DOM in ReactJS?**

The **Virtual DOM** is an in-memory representation of the real DOM. React updates the Virtual DOM first, compares it to the previous state, and updates only the changed parts in the real DOM. This ensures faster updates and better performance.

---

### **Difference Between Shadow Copy and Deep Copy**

| Feature                | Shadow Copy                     | Deep Copy                     |
|------------------------|----------------------------------|-------------------------------|
| Definition             | Duplicates references           | Duplicates actual objects     |
| Independence           | Changes in copy affect original | Changes in copy don’t affect  |
| Methods                | `Object.assign()`, spread operator | `JSON.parse(JSON.stringify())`|

---

### **CRUD Operation in ReactJS**

#### Example: Basic CRUD App
```jsx
const App = () => {
  const [items, setItems] = useState([]);
  const [newItem, setNewItem] = useState("");

  const addItem = () => setItems([...items, newItem]);
  const deleteItem = (index) => setItems(items.filter((_, i) => i !== index));

  return (
    <div>
      <input value={newItem} onChange={(e) => setNewItem(e.target.value)} />
      <button onClick={addItem}>Add</button>
      {items.map((item, index) => (
        <div key={index}>
          <span>{item}</span>
          <button onClick={() => deleteItem(index)}>Delete</button>
        </div>
      ))}
    </div>
  );
};
```

---

### **Difference Between Context API and Redux**

| Feature                | Context API                    | Redux                         |
|------------------------|--------------------------------|-------------------------------|
| Use Case              | Simple state sharing           | Complex state management      |
| Tooling               | Built into React               | Requires external library     |
| Learning Curve        | Easy                           | Steeper                       |

---

### **Explain Redux Components and Their Uses**

1. **Store**: Centralized state container.  
2. **Actions**: Define what to do.  
3. **Reducers**: Specify how the state changes.  
4. **Dispatch**: Sends actions to reducers.

---

### **Explain React Lifecycle Hooks**

1. **Mounting**: `componentDidMount`  
2. **Updating**: `componentDidUpdate`  
3. **Unmounting**: `componentWillUnmount`

---

### **How to Achieve Lifecycle Handling Using Function Component**

Use `useEffect` to replicate lifecycle methods.  
- `componentDidMount`: `useEffect(() => {}, []);`  
- `componentWillUnmount`: Cleanup function in `useEffect`.  

---

### **What is Memorization in ReactJS**

Memorization optimizes performance by caching values or functions to avoid unnecessary computations.

---

### **Difference Between useCallback and useMemo**

| Feature        | `useCallback`                     | `useMemo`                      |
|----------------|-----------------------------------|---------------------------------|
| Purpose        | Memoizes functions                | Memoizes values                |

---

### **Improving Performance in React Applications**

1. Use **React.memo**, **useCallback**, and **useMemo**.  
2. Split code with **lazy loading**.  
3. Optimize component rendering.

---

### **Difference Between Props and State in ReactJS**

| Feature       | Props                       | State                          |
|---------------|-----------------------------|--------------------------------|
| Mutability    | Immutable                  | Mutable                       |
| Source        | Parent component           | Within the component          |

---

### **What is Props Drilling?**

Passing props through multiple levels of components unnecessarily.  

#### How to Reduce Props Drilling:
1. Use **Context API**.  
2. Leverage state management libraries like **Redux**.

---

### **Updating Parent Data from Child**

Use callback functions passed as props.

```jsx
const Parent = () => {
  const [data, setData] = useState("");
  return <Child updateData={setData} />;
};

const Child = ({ updateData }) => (
  <button onClick={() => updateData("New Data")}>Update</button>
);
```

---

### **API Calls in React**

```jsx
useEffect(() => {
  fetch("https://api.example.com")
    .then((res) => res.json())
    .then((data) => console.log(data));
}, []);
```

#### Calling Multiple Promises:
```jsx
Promise.all([fetch(url1), fetch(url2)]).then(([res1, res2]) => console.log(res1, res2));
```

---

### **Difference Between Map, Filter, and Reduce**

| Feature      | `map`               | `filter`              | `reduce`                     |
|--------------|---------------------|-----------------------|------------------------------|
| Use Case     | Transform items     | Filter items          | Aggregate values             |

---

### **Call, Apply, and Bind**

| Feature       | `call`                     | `apply`                     | `bind`                      |
|---------------|----------------------------|-----------------------------|-----------------------------|
| Syntax        | `fn.call(context, ...args)`| `fn.apply(context, [args])` | `fn.bind(context)`          |

---

### **Array Operations Example**

#### Example: Array Methods
```jsx
const numbers = [1, 2, 3];
const doubled = numbers.map((num) => num * 2);
const filtered = numbers.filter((num) => num > 1);
const sum = numbers.reduce((acc, num) => acc + num, 0);
console.log(doubled, filtered, sum);
```

### **React Hooks Rules**

To use hooks correctly, follow these rules:  
1. **Only Call Hooks at the Top Level**: Don't call hooks inside loops, conditions, or nested functions.  
2. **Only Call Hooks in React Functions**: Hooks should only be used in functional components or custom hooks.  
3. **Follow Dependencies**: Add dependencies when using hooks like `useEffect` to avoid unexpected behavior.  

---

### **Purpose of `useEffect` Hook in React**

The `useEffect` hook lets you perform side effects in function components, such as fetching data, updating the DOM, or subscribing to events. It replaces lifecycle methods like `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount`.

#### Example: Basic Usage
```jsx
import React, { useState, useEffect } from "react";

const App = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `You clicked ${count} times`;
  }, [count]); // Dependency array

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Click Me</button>
    </div>
  );
};
export default App;
```

#### Explanation of `[]` Dependency Array:
- **Empty Array (`[]`)**: Runs the effect only once after the component mounts.  
- **Dependencies in Array**: Re-runs the effect whenever specified dependencies change.  
- **Omitting Array**: Effect runs on every render (rarely recommended).

---

### **What is Redux, and How Does It Relate to React?**

Redux is a state management library that provides a predictable and centralized way to manage application state. It works seamlessly with React using the **React-Redux** library.

#### Redux Key Concepts:
1. **Store**: Holds the global state.  
2. **Actions**: Describe what to do.  
3. **Reducers**: Specify how to update state based on actions.  
4. **Dispatch**: Triggers actions to update state.  

---

#### Example: Managing a Todo App with Redux

**1. Setup Redux:**
Install dependencies:
```bash
npm install redux react-redux
```

**2. Create Redux Store:**
```jsx
import { createStore } from "redux";

// Initial State
const initialState = {
  todos: [],
};

// Reducer
const todoReducer = (state = initialState, action) => {
  switch (action.type) {
    case "ADD_TODO":
      return { ...state, todos: [...state.todos, action.payload] };
    case "REMOVE_TODO":
      return { ...state, todos: state.todos.filter((_, i) => i !== action.index) };
    default:
      return state;
  }
};

// Create Store
const store = createStore(todoReducer);
export default store;
```

**3. Create Actions:**
```jsx
export const addTodo = (todo) => ({ type: "ADD_TODO", payload: todo });
export const removeTodo = (index) => ({ type: "REMOVE_TODO", index });
```

**4. Connect React with Redux:**
```jsx
import React from "react";
import { Provider, useDispatch, useSelector } from "react-redux";
import store, { addTodo, removeTodo } from "./store";

const App = () => {
  const dispatch = useDispatch();
  const todos = useSelector((state) => state.todos);

  const handleAddTodo = () => dispatch(addTodo("New Todo"));
  const handleRemoveTodo = (index) => dispatch(removeTodo(index));

  return (
    <div>
      <button onClick={handleAddTodo}>Add Todo</button>
      <ul>
        {todos.map((todo, index) => (
          <li key={index}>
            {todo} <button onClick={() => handleRemoveTodo(index)}>Remove</button>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default () => (
  <Provider store={store}>
    <App />
  </Provider>
);
```

---

### **Role of `useReducer` Hook in React**

`useReducer` is an alternative to `useState` for managing complex state logic. It works similarly to Redux but is local to the component.

#### Example:
```jsx
import React, { useReducer } from "react";

const reducer = (state, action) => {
  switch (action.type) {
    case "INCREMENT":
      return { count: state.count + 1 };
    case "DECREMENT":
      return { count: state.count - 1 };
    default:
      return state;
  }
};

const App = () => {
  const [state, dispatch] = useReducer(reducer, { count: 0 });

  return (
    <div>
      <button onClick={() => dispatch({ type: "DECREMENT" })}>-</button>
      <span>{state.count}</span>
      <button onClick={() => dispatch({ type: "INCREMENT" })}>+</button>
    </div>
  );
};
export default App;
```

---

### **Purpose of `useContext` Hook in React**

The `useContext` hook allows components to consume values from React's Context API without needing to pass props down manually.

#### Example:
```jsx
import React, { createContext, useContext } from "react";

const ThemeContext = createContext("light");

const App = () => {
  const theme = useContext(ThemeContext);

  return <div>The theme is {theme}</div>;
};

export default () => (
  <ThemeContext.Provider value="dark">
    <App />
  </ThemeContext.Provider>
);
```

---

### **Significance of `useLayoutEffect` Hook**

`useLayoutEffect` runs synchronously after all DOM mutations. It’s useful for measurements and updates before the browser paints.

#### Example:
```jsx
import React, { useLayoutEffect, useRef } from "react";

const App = () => {
  const divRef = useRef();

  useLayoutEffect(() => {
    console.log("Div height:", divRef.current.offsetHeight);
  });

  return <div ref={divRef}>Hello, World!</div>;
};
export default App;
```

#### Difference from `useEffect`:
- `useEffect`: Runs after the browser repaints.  
- `useLayoutEffect`: Runs before the browser repaints, blocking visual updates until complete.

### **What is Error Boundary in React? How Does It Help in Error Handling?**

An **Error Boundary** is a React component that catches JavaScript errors in its child component tree, logs them, and displays a fallback UI instead of crashing the application. It helps ensure that one broken part of the UI doesn’t break the entire app.

#### Key Points:
1. Error boundaries are class components that implement either `componentDidCatch` or `getDerivedStateFromError`.  
2. They only catch errors during rendering, lifecycle methods, or constructors, not in event handlers.

#### Example:
```jsx
import React, { Component } from "react";

class ErrorBoundary extends Component {
  constructor(props) {
    super(props);
    this.state = { hasError: false };
  }

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    console.error("Error caught:", error, info);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

const BuggyComponent = () => {
  throw new Error("Oops!");
};

const App = () => (
  <ErrorBoundary>
    <BuggyComponent />
  </ErrorBoundary>
);
export default App;
```

---

### **What is the Significance of React's Strict Mode?**

**Strict Mode** is a tool for highlighting potential issues in an application. It runs additional checks and warnings in development mode but does not affect the production build.

#### Benefits:
1. Identifies unsafe lifecycle methods.  
2. Warns about legacy string ref usage.  
3. Detects unexpected side effects by rendering components twice.  

#### Usage:
```jsx
import React from "react";

const App = () => (
  <React.StrictMode>
    <MyComponent />
  </React.StrictMode>
);
```

---

### **What is Server-Side Rendering (SSR) in React? Why is It Important?**

**SSR** involves rendering React components on the server as HTML and sending them to the browser. The client hydrates the HTML into a React application.

#### Importance:
1. **Improved SEO**: Search engines can index the rendered HTML.  
2. **Faster Initial Load**: Users see content quicker.  
3. **Better Performance**: Reduces JavaScript workload on the client.  

#### Example Using Next.js:
```jsx
import React from "react";

const Page = ({ data }) => <div>{data}</div>;

export async function getServerSideProps() {
  const res = await fetch("https://api.example.com/data");
  const data = await res.json();
  return { props: { data } };
}

export default Page;
```

---

### **What is the Purpose of React Portals? Provide an Example**

React **Portals** allow you to render components outside of the parent DOM hierarchy, typically useful for modals, tooltips, or overlays.

#### Example:
```jsx
import React from "react";
import ReactDOM from "react-dom";

const Modal = ({ isOpen, children }) =>
  isOpen
    ? ReactDOM.createPortal(
        <div className="modal">{children}</div>,
        document.getElementById("modal-root")
      )
    : null;

const App = () => (
  <div>
    <h1>Main App</h1>
    <Modal isOpen={true}>
      <h2>This is a modal!</h2>
    </Modal>
  </div>
);

export default App;
```
**HTML Structure**:
```html
<div id="root"></div>
<div id="modal-root"></div>
```

---

### **What is the Purpose of Using PropTypes in React?**

**PropTypes** help validate the props passed to a component, ensuring that the correct types of data are provided.

#### Example:
```jsx
import React from "react";
import PropTypes from "prop-types";

const Greeting = ({ name, age }) => (
  <div>
    Hello {name}, you are {age} years old.
  </div>
);

Greeting.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number,
};

export default Greeting;
```

---

### **Differences Between React.forwardRef and React.createRef**

| Feature               | `React.forwardRef`                          | `React.createRef`                 |
|-----------------------|---------------------------------------------|-----------------------------------|
| Purpose               | Pass refs to child components              | Create a reference to a DOM node |
| Usage                 | Used with functional components            | Used in both functional and class components |
| Reusability           | Shared between parent and child            | Typically specific to a component |

#### Example:
**`React.forwardRef`:**
```jsx
import React, { forwardRef } from "react";

const Input = forwardRef((props, ref) => <input ref={ref} {...props} />);

const App = () => {
  const inputRef = React.createRef();
  return (
    <div>
      <Input ref={inputRef} />
      <button onClick={() => inputRef.current.focus()}>Focus Input</button>
    </div>
  );
};
export default App;
```

**`React.createRef`:**
```jsx
import React from "react";

class App extends React.Component {
  constructor() {
    super();
    this.inputRef = React.createRef();
  }

  focusInput = () => this.inputRef.current.focus();

  render() {
    return (
      <div>
        <input ref={this.inputRef} />
        <button onClick={this.focusInput}>Focus Input</button>
      </div>
    );
  }
}
export default App;
```

---

### **What is the Purpose of React.memo() in React?**

`React.memo()` is a higher-order component that prevents unnecessary re-renders of a component by memoizing its output based on props.

#### Example:
```jsx
import React from "react";

const Child = React.memo(({ count }) => {
  console.log("Child rendered");
  return <div>Count: {count}</div>;
});

const App = () => {
  const [count, setCount] = React.useState(0);
  const [other, setOther] = React.useState(0);

  return (
    <div>
      <Child count={count} />
      <button onClick={() => setCount(count + 1)}>Increment Count</button>
      <button onClick={() => setOther(other + 1)}>Change Other</button>
    </div>
  );
};
export default App;
```
In the above example, the `Child` component will only re-render if the `count` prop changes.

### **What are Refs in React? When Would You Use Them?**

**Refs** (short for references) in React provide a way to directly access a DOM element or an instance of a component. They are created using `React.createRef` or the `useRef` hook.

#### Common Use Cases for Refs:
1. **Accessing DOM Elements**: Focus input fields or measure DOM elements.  
2. **Storing Mutable Values**: Retain values between renders without triggering re-renders.  
3. **Integrating Third-Party Libraries**: Control non-React elements like charts or modals.  

#### Example:
```jsx
import React, { useRef } from "react";

const App = () => {
  const inputRef = useRef();

  const handleFocus = () => inputRef.current.focus();

  return (
    <div>
      <input ref={inputRef} placeholder="Focus me!" />
      <button onClick={handleFocus}>Focus Input</button>
    </div>
  );
};
export default App;
```

---

### **What is the Significance of the `defaultProps` Property in React Components?**

`defaultProps` allows you to specify default values for props if none are provided. It ensures components behave predictably even if props are omitted.

#### Example:
```jsx
import React from "react";

const Greeting = ({ name }) => <div>Hello, {name}!</div>;

Greeting.defaultProps = {
  name: "Guest",
};

export default Greeting;
```
**Usage**: If no `name` prop is passed, it will default to `"Guest"`.

---

### **What is the Role of the `setState()` Method in React?**

The `setState()` method is used to update the state of a class component. It triggers a re-render, updating the UI to reflect the new state.

#### Key Points:
1. State updates are **asynchronous**.
2. Use the callback form of `setState` if relying on the previous state.

#### Example:
```jsx
import React, { Component } from "react";

class Counter extends Component {
  state = { count: 0 };

  increment = () => {
    this.setState((prevState) => ({ count: prevState.count + 1 }));
  };

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
export default Counter;
```

---

### **Differences Between Functional Components and Class Components in React**

| Feature                | Functional Components       | Class Components             |
|------------------------|-----------------------------|-----------------------------|
| Syntax                 | Function-based             | Class-based                 |
| State Management       | Use hooks (`useState`)     | Use `state` and `setState`  |
| Lifecycle Methods      | `useEffect` replaces methods | Lifecycle methods like `componentDidMount` |
| Boilerplate            | Minimal                    | More verbose                |
| Performance            | Slightly faster            | Slightly slower             |

#### Examples:
**Functional Component**:
```jsx
import React, { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
};
export default Counter;
```

**Class Component**:
```jsx
import React, { Component } from "react";

class Counter extends Component {
  state = { count: 0 };

  increment = () => this.setState({ count: this.state.count + 1 });

  render() {
    return (
      <div>
        <p>Count: {this.state.count}</p>
        <button onClick={this.increment}>Increment</button>
      </div>
    );
  }
}
export default Counter;
```

---

### **Advantages of Using Arrow Functions in React Component Methods**

1. **Automatic Binding**: Arrow functions inherit the context of `this` from their parent, eliminating the need for manual binding.  
2. **Conciseness**: Arrow functions are shorter and cleaner.  
3. **Consistency**: Prevents bugs caused by the incorrect use of `this`.

#### Example:
```jsx
class App extends React.Component {
  handleClick = () => {
    console.log("Clicked", this);
  };

  render() {
    return <button onClick={this.handleClick}>Click Me</button>;
  }
}
```

---

### **Difference Between `useEffect` and `useLayoutEffect`**

| Feature               | `useEffect`                          | `useLayoutEffect`                      |
|-----------------------|---------------------------------------|---------------------------------------|
| Timing                | Runs after the DOM has been painted  | Runs before the DOM is painted        |
| Use Case              | Non-visual side effects (e.g., API calls) | Visual updates (e.g., animations, layout calculations) |
| Blocking UI Updates   | No                                   | Yes                                   |

#### Example:
```jsx
import React, { useEffect, useLayoutEffect } from "react";

const App = () => {
  useEffect(() => {
    console.log("useEffect");
  });

  useLayoutEffect(() => {
    console.log("useLayoutEffect");
  });

  return <div>Hello, World!</div>;
};
export default App;
```
**Output Order**: `useLayoutEffect` runs before `useEffect`.

---

### **What is the Purpose of the `useCallback` Hook in React?**

`useCallback` memoizes a function to prevent it from being recreated on every render, optimizing performance by ensuring functions are only re-created when their dependencies change.

#### Example:
```jsx
import React, { useState, useCallback } from "react";

const Child = React.memo(({ onClick }) => {
  console.log("Child rendered");
  return <button onClick={onClick}>Click Child</button>;
});

const App = () => {
  const [count, setCount] = useState(0);
  const handleClick = useCallback(() => {
    console.log("Button clicked");
  }, []);

  return (
    <div>
      <button onClick={() => setCount(count + 1)}>Parent Count: {count}</button>
      <Child onClick={handleClick} />
    </div>
  );
};
export default App;
```
In this example, `Child` does not re-render unnecessarily because `useCallback` ensures that `handleClick` has the same reference between renders.

### **What is React Fiber?**

**React Fiber** is the new reconciliation algorithm in React that was introduced in React 16. It reworks how React updates the DOM by making the rendering process more incremental and prioritizing updates, which improves performance, especially for complex applications.

#### Key Features:
1. **Incremental Rendering**: React Fiber allows React to split rendering work into units, so the browser doesn't become unresponsive. This makes React capable of rendering large and complex UI updates in chunks without blocking the main thread.
2. **Prioritized Updates**: Fiber allows React to prioritize updates and handle high-priority tasks (like animations or user input) over low-priority ones (like data fetching).
3. **Concurrency**: It lays the foundation for **concurrent rendering** in React, meaning React can pause work and come back to it later, which allows for smoother user experiences.
4. **Error Boundaries**: Fiber also improves the error handling system by enabling features like **Error Boundaries**, which catch and gracefully handle errors during rendering.

Fiber was a complete rewrite of React's core algorithm, which helped React provide better performance, especially in complex scenarios like large-scale apps and interactive UIs.

---

### **What is the Significance of the `dangerouslySetInnerHTML` Attribute in React?**

`dangerouslySetInnerHTML` is a special attribute in React that is used to set HTML content directly into the DOM. It is called "dangerously" because it can lead to **cross-site scripting (XSS)** vulnerabilities if not handled properly.

#### When to Use:
1. **Injecting Raw HTML**: If you need to render HTML from external sources, such as an HTML string from a database or API, use `dangerouslySetInnerHTML`.
2. **Sanitizing Input**: Always sanitize the HTML input to avoid XSS attacks before passing it to `dangerouslySetInnerHTML`.

#### Example:
```jsx
const MyComponent = () => {
  const rawHTML = "<div><h1>Hello World</h1></div>";
  return <div dangerouslySetInnerHTML={{ __html: rawHTML }} />;
};

export default MyComponent;
```
**Note**: Use it cautiously, as injecting unsanitized HTML into the DOM can open the app to security vulnerabilities.

---

### **What is the Purpose of the `getDerivedStateFromError` Lifecycle Method in React?**

`getDerivedStateFromError` is a static lifecycle method used in **Error Boundaries** to handle errors in React components. It is called when a component's child component throws an error during rendering, lifecycle methods, or constructors.

#### Purpose:
- **Update State in Response to Errors**: It allows you to modify the state of the component when an error occurs.
- **Display Fallback UI**: It enables you to show a fallback UI to the user instead of the entire application crashing.

#### Key Features:
- **Static method**: It doesn’t have access to `this`, and can only return an object to update state based on the error.
- **Used with `componentDidCatch`**: `getDerivedStateFromError` is often paired with `componentDidCatch` for logging the error.

#### Example:
```jsx
import React, { Component } from "react";

class ErrorBoundary extends Component {
  static getDerivedStateFromError(error) {
    // Update state to indicate an error has occurred
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    // Log the error
    console.error("Error caught: ", error, info);
  }

  render() {
    if (this.state.hasError) {
      return <h1>Something went wrong.</h1>;
    }
    return this.props.children;
  }
}

const BuggyComponent = () => {
  throw new Error("Error in child component");
  return <div>Buggy Component</div>;
};

const App = () => (
  <ErrorBoundary>
    <BuggyComponent />
  </ErrorBoundary>
);

export default App;
```

In this example:
- `getDerivedStateFromError` updates the state when an error is caught.
- `componentDidCatch` logs the error to an external service.
- The fallback UI (`<h1>Something went wrong.</h1>`) is displayed instead of the broken component.

---

# Todo App

Let's create a simple **To-Do App** using **React** and **Redux**. We'll utilize **local storage** for saving the tasks persistently and leverage features like **Redux** state management and **React lifecycle methods** (like `useEffect`).

Here’s a step-by-step guide:

### Step 1: Set up the project

1. **Create a new React app**:
```bash
npx create-react-app todo-app
cd todo-app
npm install redux react-redux
```

2. **Project Structure**:
```
src/
  |-- components/
       |-- TodoList.js
       |-- TodoItem.js
       |-- TodoInput.js
  |-- store/
       |-- actions.js
       |-- reducer.js
       |-- store.js
  |-- App.js
```

### Step 2: Set up Redux

1. **Create actions (src/store/actions.js)**:
```js
// Actions for adding, removing, and toggling tasks
export const ADD_TODO = 'ADD_TODO';
export const REMOVE_TODO = 'REMOVE_TODO';
export const TOGGLE_TODO = 'TOGGLE_TODO';

// Action creators
export const addTodo = (task) => ({
  type: ADD_TODO,
  payload: task,
});

export const removeTodo = (id) => ({
  type: REMOVE_TODO,
  payload: id,
});

export const toggleTodo = (id) => ({
  type: TOGGLE_TODO,
  payload: id,
});
```

2. **Create reducer (src/store/reducer.js)**:
```js
import { ADD_TODO, REMOVE_TODO, TOGGLE_TODO } from './actions';

const initialState = {
  todos: JSON.parse(localStorage.getItem('todos')) || [],
};

const todoReducer = (state = initialState, action) => {
  switch (action.type) {
    case ADD_TODO:
      const newTodos = [...state.todos, action.payload];
      localStorage.setItem('todos', JSON.stringify(newTodos));
      return { ...state, todos: newTodos };
    case REMOVE_TODO:
      const filteredTodos = state.todos.filter(todo => todo.id !== action.payload);
      localStorage.setItem('todos', JSON.stringify(filteredTodos));
      return { ...state, todos: filteredTodos };
    case TOGGLE_TODO:
      const toggledTodos = state.todos.map(todo =>
        todo.id === action.payload ? { ...todo, completed: !todo.completed } : todo
      );
      localStorage.setItem('todos', JSON.stringify(toggledTodos));
      return { ...state, todos: toggledTodos };
    default:
      return state;
  }
};

export default todoReducer;
```

3. **Create store (src/store/store.js)**:
```js
import { createStore } from 'redux';
import todoReducer from './reducer';

const store = createStore(todoReducer);

export default store;
```

### Step 3: Create React Components

1. **TodoItem Component (src/components/TodoItem.js)**:
```js
import React from 'react';

const TodoItem = ({ todo, onToggle, onRemove }) => {
  return (
    <div>
      <input
        type="checkbox"
        checked={todo.completed}
        onChange={() => onToggle(todo.id)}
      />
      <span style={{ textDecoration: todo.completed ? 'line-through' : 'none' }}>
        {todo.task}
      </span>
      <button onClick={() => onRemove(todo.id)}>Delete</button>
    </div>
  );
};

export default TodoItem;
```

2. **TodoInput Component (src/components/TodoInput.js)**:
```js
import React, { useState } from 'react';
import { useDispatch } from 'react-redux';
import { addTodo } from '../store/actions';

const TodoInput = () => {
  const [task, setTask] = useState('');
  const dispatch = useDispatch();

  const handleSubmit = (e) => {
    e.preventDefault();
    if (task) {
      dispatch(addTodo({
        id: Date.now(),
        task,
        completed: false,
      }));
      setTask('');
    }
  };

  return (
    <form onSubmit={handleSubmit}>
      <input
        type="text"
        value={task}
        onChange={(e) => setTask(e.target.value)}
        placeholder="Add a task"
      />
      <button type="submit">Add Task</button>
    </form>
  );
};

export default TodoInput;
```

3. **TodoList Component (src/components/TodoList.js)**:
```js
import React from 'react';
import { useSelector, useDispatch } from 'react-redux';
import { removeTodo, toggleTodo } from '../store/actions';
import TodoItem from './TodoItem';

const TodoList = () => {
  const todos = useSelector(state => state.todos);
  const dispatch = useDispatch();

  const handleToggle = (id) => {
    dispatch(toggleTodo(id));
  };

  const handleRemove = (id) => {
    dispatch(removeTodo(id));
  };

  return (
    <div>
      {todos.map(todo => (
        <TodoItem
          key={todo.id}
          todo={todo}
          onToggle={handleToggle}
          onRemove={handleRemove}
        />
      ))}
    </div>
  );
};

export default TodoList;
```

### Step 4: Set up the main App (src/App.js)
```js
import React, { useEffect } from 'react';
import { Provider } from 'react-redux';
import TodoInput from './components/TodoInput';
import TodoList from './components/TodoList';
import store from './store/store';

const App = () => {
  // Using useEffect to handle initial setup like local storage or API calls.
  useEffect(() => {
    const storedTodos = JSON.parse(localStorage.getItem('todos'));
    if (storedTodos) {
      console.log('Loaded todos from localStorage');
    }
  }, []);

  return (
    <Provider store={store}>
      <div>
        <h1>Todo App</h1>
        <TodoInput />
        <TodoList />
      </div>
    </Provider>
  );
};

export default App;
```

### Step 5: Running the Application

To run the app, follow these steps:

1. Install dependencies if you haven't already:
```bash
npm install
```

2. Start the app:
```bash
npm start
```

Now, you should be able to see a basic **To-Do App** where:
- You can add tasks.
- Mark tasks as completed.
- Remove tasks.
- The tasks persist even after a page refresh, using **local storage**.

### Key Features Implemented:
1. **Redux for state management**: We used `redux` to manage the app's state (tasks), actions to add, remove, and toggle tasks, and reducer to update the state.
2. **Local Storage**: Tasks are stored in the browser's local storage for persistence across page reloads.
3. **React Components**: The app is structured into smaller components (`TodoInput`, `TodoList`, `TodoItem`).
4. **React `useEffect`**: We used `useEffect` to load the tasks from local storage when the app starts.
5. **Error Boundaries and `dangerouslySetInnerHTML` (optional)**: Not specifically implemented in this simple version, but these features can be added as part of error handling and rendering raw HTML in other parts of the app.

This is a basic structure that you can expand with more advanced features like **filters** (all, completed, pending tasks) and more complex **state management** or **API integration** in the future.
