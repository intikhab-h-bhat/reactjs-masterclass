# Complete ReactJS Beginner Lecture Series

## Course Overview

**Duration:** 2 Sessions × 2 Hours Each  
**Prerequisites:** HTML, CSS, JavaScript  
**Target Audience:** Programming beginners with web development basics

---

# Session 1: Introduction to React & Getting Started
**Duration:** 2 Hours

## 📋 Session Agenda
1. What is ReactJS? (20 min)
2. Why do we need React? (15 min)
3. Setting up Development Environment (25 min)
4. Your First React App (30 min)
5. Understanding JSX (20 min)
6. Components Basics (25 min)
7. Session Summary & Q&A (5 min)

## 🎯 Learning Goals
By the end of this session, you will:
- Understand what React is and why it's useful
- Set up a complete React development environment
- Create your first React application
- Write JSX syntax confidently
- Build simple React components

---

## 1. What is ReactJS?

### Think of React Like Building with LEGO Blocks

Imagine you're building a house with LEGO blocks. Instead of creating one massive, complicated structure, you build small, reusable pieces:
- A door piece
- A window piece  
- A roof piece
- A wall piece

You can then combine these pieces to build different houses, and if you need to change something, you only modify the specific piece, not the entire house.

**React works the same way!**

### 🔍 Official Definition
React is a JavaScript library for building user interfaces, especially web applications. It lets you create reusable UI components and manage how your app responds to user interactions.

### Key Concepts:
- **Component-Based:** Build encapsulated components that manage their own state
- **Declarative:** Describe what the UI should look like, not how to achieve it
- **Learn Once, Write Anywhere:** Use React for web, mobile (React Native), and more

### Real-World Example
Think about Facebook (where React was created):
- The "Like" button appears everywhere
- The comment section is reused across posts
- The navigation bar is the same on every page

Instead of writing the same code over and over, React lets you create these as reusable components!

---

## 2. Why Do We Need React?

### 🤔 The Problem with Vanilla JavaScript

Let's look at a simple counter example:

**With Vanilla JavaScript:**
```html
<!DOCTYPE html>
<html>
<head>
    <title>Counter App</title>
</head>
<body>
    <div id="app">
        <h1>Counter: <span id="count">0</span></h1>
        <button id="increment">+</button>
        <button id="decrement">-</button>
    </div>

    <script>
        let count = 0;
        const countDisplay = document.getElementById('count');
        const incrementBtn = document.getElementById('increment');
        const decrementBtn = document.getElementById('decrement');

        incrementBtn.addEventListener('click', () => {
            count++;
            countDisplay.textContent = count;
        });

        decrementBtn.addEventListener('click', () => {
            count--;
            countDisplay.textContent = count;
        });
    </script>
</body>
</html>
```

**Problems with this approach:**
1. **Manual DOM manipulation** - You have to manually update the display
2. **Scattered code** - Logic is spread across multiple places
3. **Hard to maintain** - As the app grows, it becomes messy
4. **Repetitive** - You write similar code over and over

### 🚀 React's Solution

React solves these problems by:

1. **Automatic UI Updates:** When data changes, React automatically updates the UI
2. **Component Organization:** Keep related code together
3. **Reusability:** Write once, use everywhere
4. **Predictable:** Always know what your UI will look like based on your data

### Benefits of Using React:

#### 🎯 **Predictable**
```javascript
// If count is 5, the UI will ALWAYS show 5
// No manual DOM manipulation needed
```

#### ♻️ **Reusable**
```javascript
// Create a Button component once
// Use it everywhere: <Button>, <Button>, <Button>
```

#### 🔧 **Maintainable**
```javascript
// All button logic is in one place
// Easy to find and fix bugs
```

#### ⚡ **Fast**
```javascript
// React only updates what actually changed
// Not the entire page
```

---

## 3. Setting Up Development Environment

### 🛠️ Tools We Need

1. **Node.js** - JavaScript runtime
2. **npm** - Package manager
3. **VS Code** - Code editor
4. **Create React App** - React project generator

### Step 1: Install Node.js

1. Go to [nodejs.org](https://nodejs.org)
2. Download the LTS (Long Term Support) version
3. Install it (default settings are fine)
4. Verify installation:

```bash
node --version
npm --version
```

### Step 2: Set Up VS Code

1. Download VS Code from [code.visualstudio.com](https://code.visualstudio.com)
2. Install these helpful extensions:
   - **ES7+ React/Redux/React-Native snippets**
   - **Bracket Pair Colorizer**
   - **Auto Rename Tag**
   - **Prettier - Code formatter**

### Step 3: Create Your First React App

```bash
# Create a new React app
npx create-react-app my-first-react-app

# Navigate to the project folder
cd my-first-react-app

# Start the development server
npm start
```

### 🎉 What Just Happened?

Create React App set up:
- A complete React project structure
- Development server with hot reloading
- Build tools (Webpack, Babel)
- Testing environment

### Project Structure Overview

```
my-first-react-app/
├── public/
│   ├── index.html
│   └── favicon.ico
├── src/
│   ├── App.js
│   ├── App.css
│   ├── index.js
│   └── index.css
├── package.json
└── README.md
```

**Key Files:**
- `public/index.html` - The main HTML file
- `src/index.js` - Entry point of your React app
- `src/App.js` - Main App component
- `package.json` - Project dependencies and scripts

---

## 4. Your First React App

### 🔍 Understanding the Default App

Let's look at `src/App.js`:

```javascript
import logo from './logo.svg';
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <img src={logo} className="App-logo" alt="logo" />
        <p>
          Edit <code>src/App.js</code> and save to reload.
        </p>
        <a
          className="App-link"
          href="https://reactjs.org"
          target="_blank"
          rel="noopener noreferrer"
        >
          Learn React
        </a>
      </header>
    </div>
  );
}

export default App;
```

### 🎯 Let's Break It Down

1. **Import statements** - Bring in dependencies
2. **Function component** - A JavaScript function that returns JSX
3. **Return statement** - What gets displayed on screen
4. **Export statement** - Makes the component available to other files

### 🛠️ Exercise 1: Customize Your App

Replace the content of `src/App.js` with:

```javascript
import './App.css';

function App() {
  return (
    <div className="App">
      <header className="App-header">
        <h1>Welcome to My React Journey!</h1>
        <p>This is my first React application.</p>
        <p>Today's date: {new Date().toLocaleDateString()}</p>
      </header>
    </div>
  );
}

export default App;
```

**Save the file and watch it update automatically!** 🎉

---

## 5. Understanding JSX

### 🤔 What is JSX?

JSX stands for **JavaScript XML**. It's a syntax extension that lets you write HTML-like code inside JavaScript.

### JSX vs HTML Comparison

**HTML:**
```html
<div class="container">
    <h1>Hello World</h1>
    <p>This is a paragraph</p>
</div>
```

**JSX:**
```javascript
<div className="container">
    <h1>Hello World</h1>
    <p>This is a paragraph</p>
</div>
```

### 🔍 Key Differences

1. **className instead of class**
```javascript
// HTML
<div class="my-class">

// JSX
<div className="my-class">
```

2. **Self-closing tags need forward slash**
```javascript
// HTML
<img src="image.jpg">
<br>

// JSX
<img src="image.jpg" />
<br />
```

3. **JavaScript expressions in curly braces**
```javascript
const name = "John";
const age = 25;

// JSX
<div>
    <h1>Hello {name}</h1>
    <p>You are {age} years old</p>
    <p>Next year you'll be {age + 1}</p>
</div>
```

### 🎯 JSX Rules

1. **Must return a single parent element**
```javascript
// ❌ Wrong - Multiple root elements
function App() {
  return (
    <h1>Title</h1>
    <p>Paragraph</p>
  );
}

// ✅ Correct - Single root element
function App() {
  return (
    <div>
      <h1>Title</h1>
      <p>Paragraph</p>
    </div>
  );
}

// ✅ Also correct - React Fragment
function App() {
  return (
    <>
      <h1>Title</h1>
      <p>Paragraph</p>
    </>
  );
}
```

2. **JavaScript expressions go in curly braces**
```javascript
const greeting = "Hello";
const user = { name: "Alice", age: 30 };

return (
  <div>
    <h1>{greeting} {user.name}!</h1>
    <p>Age: {user.age}</p>
    <p>Born in: {2024 - user.age}</p>
  </div>
);
```

3. **Inline styles are objects**
```javascript
// HTML
<div style="color: red; font-size: 20px;">

// JSX
<div style={{color: 'red', fontSize: '20px'}}>
```

### 🛠️ Exercise 2: JSX Practice

Create a personal introduction using JSX:

```javascript
function App() {
  const firstName = "Your Name";
  const lastName = "Your Last Name";
  const hobbies = ["Reading", "Gaming", "Coding"];
  const favoriteColor = "blue";

  return (
    <div style={{padding: '20px', fontFamily: 'Arial'}}>
      <h1 style={{color: favoriteColor}}>
        Hello, I'm {firstName} {lastName}
      </h1>
      <p>My hobbies include:</p>
      <ul>
        <li>{hobbies[0]}</li>
        <li>{hobbies[1]}</li>
        <li>{hobbies[2]}</li>
      </ul>
      <p>Today is {new Date().toDateString()}</p>
    </div>
  );
}
```

---

## 6. Components Basics

### 🧩 What is a Component?

A component is like a JavaScript function that returns JSX. It's a piece of UI that you can reuse throughout your app.

### 🏠 Real-World Analogy

Think of a house:
- **House** = Your App
- **Rooms** = Components (Kitchen, Bedroom, Bathroom)
- **Furniture** = Smaller components (Chair, Table, Bed)

Each room has a specific purpose and can be designed independently!

### 📝 Two Ways to Create Components

#### 1. Function Components (Recommended)
```javascript
function Welcome() {
  return <h1>Hello, World!</h1>;
}
```

#### 2. Arrow Function Components
```javascript
const Welcome = () => {
  return <h1>Hello, World!</h1>;
}
```

### 🎯 Component Rules

1. **Component names must start with a capital letter**
```javascript
// ✅ Correct
function MyComponent() { }

// ❌ Wrong
function myComponent() { }
```

2. **Components must return JSX**
```javascript
function MyComponent() {
  return <div>Hello!</div>;
}
```

3. **Use components like HTML tags**
```javascript
function App() {
  return (
    <div>
      <MyComponent />
      <MyComponent />
    </div>
  );
}
```

### 🛠️ Exercise 3: Creating Your First Component

Let's create a simple greeting component:

```javascript
// Create a new file: src/Greeting.js
function Greeting() {
  return (
    <div style={{
      padding: '20px',
      border: '2px solid #007bff',
      borderRadius: '10px',
      margin: '10px',
      textAlign: 'center'
    }}>
      <h2>👋 Hello There!</h2>
      <p>Welcome to React Components!</p>
    </div>
  );
}

export default Greeting;
```

**Now use it in App.js:**
```javascript
import Greeting from './Greeting';

function App() {
  return (
    <div>
      <h1>My App</h1>
      <Greeting />
      <Greeting />
      <Greeting />
    </div>
  );
}

export default App;
```

### 🎯 Multiple Components Example

Let's create a simple profile card:

```javascript
// Header component
function Header() {
  return (
    <header style={{backgroundColor: '#282c34', color: 'white', padding: '20px'}}>
      <h1>My Profile</h1>
    </header>
  );
}

// ProfileCard component
function ProfileCard() {
  return (
    <div style={{
      border: '1px solid #ddd',
      borderRadius: '8px',
      padding: '20px',
      margin: '20px',
      textAlign: 'center'
    }}>
      <img 
        src="https://via.placeholder.com/150" 
        alt="Profile" 
        style={{borderRadius: '50%'}}
      />
      <h2>John Doe</h2>
      <p>React Developer</p>
    </div>
  );
}

// Footer component
function Footer() {
  return (
    <footer style={{backgroundColor: '#f8f9fa', padding: '20px', textAlign: 'center'}}>
      <p>&copy; 2024 My React App</p>
    </footer>
  );
}

// Main App component
function App() {
  return (
    <div>
      <Header />
      <ProfileCard />
      <Footer />
    </div>
  );
}

export default App;
```

---

## 🔥 Quick Quiz - Session 1

Test your understanding:

1. **What is JSX?**
   - a) A new programming language
   - b) A syntax extension for JavaScript
   - c) A CSS framework
   - d) A database

2. **Which is correct JSX?**
   - a) `<div class="container">`
   - b) `<div className="container">`
   - c) `<div class-name="container">`
   - d) `<div style="color: red">`

3. **Component names must:**
   - a) Start with lowercase
   - b) Start with uppercase
   - c) Be all uppercase
   - d) Contain numbers

4. **To use JavaScript in JSX, you use:**
   - a) Parentheses ()
   - b) Square brackets []
   - c) Curly braces {}
   - d) Angle brackets <>

**Answers:** 1-b, 2-b, 3-b, 4-c

---

## 📝 Session 1 Summary

### What We Learned:
- ✅ React is a JavaScript library for building user interfaces
- ✅ React uses components - reusable pieces of UI
- ✅ JSX lets us write HTML-like syntax in JavaScript
- ✅ Components are JavaScript functions that return JSX
- ✅ Component names must start with capital letters
- ✅ We can use JavaScript expressions in JSX with curly braces

### Key Takeaways:
1. **React = Components + JSX**
2. **Components are like LEGO blocks - reusable and composable**
3. **JSX is HTML-like syntax that makes React components readable**
4. **Always start component names with capital letters**

### What's Next in Session 2:
- Props (passing data to components)
- State (making components interactive)
- Event handling (responding to user actions)
- Building a complete interactive app

### 🏠 Homework:
1. Create 3 different components (Header, Main, Footer)
2. Experiment with JSX expressions
3. Try changing styles and see the results
4. Read about React props online

---

# Session 2: Props, State, and Interactivity
**Duration:** 2 Hours

## 📋 Session Agenda
1. Review Session 1 (10 min)
2. Understanding Props (35 min)
3. Introduction to State (35 min)
4. Event Handling (25 min)
5. Building an Interactive App (30 min)
6. Session Summary & Next Steps (5 min)

## 🎯 Learning Goals
By the end of this session, you will:
- Pass data between components using props
- Understand and use React state
- Handle user interactions with events
- Build a complete interactive React application

---

## 1. Quick Review - Session 1

### 🔄 What We Covered:
- React is a component-based library
- JSX is HTML-like syntax in JavaScript
- Components are reusable pieces of UI
- Function components return JSX

### 🛠️ Quick Warm-up Exercise:
Create a simple component that displays the current time:

```javascript
function CurrentTime() {
  const now = new Date();
  return (
    <div>
      <h2>Current Time</h2>
      <p>{now.toLocaleTimeString()}</p>
    </div>
  );
}
```

---

## 2. Understanding Props

### 🎁 What are Props?

**Props** (short for properties) are like function arguments. They let you pass data from one component to another.

### 🏠 Real-World Analogy

Think of props like giving instructions to a builder:
- **You:** "Build me a house"
- **Builder:** "What color? How many rooms? What style?"
- **You:** "Blue color, 3 rooms, modern style"

Props are those specifications you give to your components!

### 📝 Basic Props Example

```javascript
// Component that receives props
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

// Using the component with props
function App() {
  return (
    <div>
      <Greeting name="Alice" />
      <Greeting name="Bob" />
      <Greeting name="Charlie" />
    </div>
  );
}
```

### 🎯 Props with Destructuring (Cleaner Syntax)

```javascript
// Instead of props.name, props.age
function UserCard({ name, age, email }) {
  return (
    <div style={{border: '1px solid #ddd', padding: '20px', margin: '10px'}}>
      <h2>{name}</h2>
      <p>Age: {age}</p>
      <p>Email: {email}</p>
    </div>
  );
}

function App() {
  return (
    <div>
      <UserCard name="John" age={25} email="john@example.com" />
      <UserCard name="Jane" age={30} email="jane@example.com" />
    </div>
  );
}
```

### 🔍 Different Types of Props

```javascript
function ComponentShowcase({ 
  title,           // String
  count,           // Number  
  isActive,        // Boolean
  items,           // Array
  user,            // Object
  onClick          // Function
}) {
  return (
    <div>
      <h1>{title}</h1>
      <p>Count: {count}</p>
      <p>Status: {isActive ? 'Active' : 'Inactive'}</p>
      <ul>
        {items.map(item => <li key={item}>{item}</li>)}
      </ul>
      <p>User: {user.name}</p>
      <button onClick={onClick}>Click me!</button>
    </div>
  );
}

// Usage
function App() {
  const handleClick = () => alert('Button clicked!');
  
  return (
    <ComponentShowcase
      title="My Component"
      count={42}
      isActive={true}
      items={['Apple', 'Banana', 'Orange']}
      user={{name: 'John', id: 1}}
      onClick={handleClick}
    />
  );
}
```

### 🛠️ Exercise 4: Product Card Component

Create a reusable product card:

```javascript
function ProductCard({ name, price, image, description, inStock }) {
  return (
    <div style={{
      border: '1px solid #ddd',
      borderRadius: '8px',
      padding: '20px',
      margin: '10px',
      width: '300px'
    }}>
      <img 
        src={image} 
        alt={name}
        style={{width: '100%', height: '200px', objectFit: 'cover'}}
      />
      <h3>{name}</h3>
      <p>{description}</p>
      <p style={{fontSize: '20px', fontWeight: 'bold', color: 'green'}}>
        ${price}
      </p>
      <p style={{color: inStock ? 'green' : 'red'}}>
        {inStock ? 'In Stock' : 'Out of Stock'}
      </p>
    </div>
  );
}

function App() {
  return (
    <div style={{display: 'flex', flexWrap: 'wrap'}}>
      <ProductCard
        name="Laptop"
        price={999}
        image="https://via.placeholder.com/300x200"
        description="High-performance laptop for coding"
        inStock={true}
      />
      <ProductCard
        name="Mouse"
        price={29}
        image="https://via.placeholder.com/300x200"
        description="Wireless gaming mouse"
        inStock={false}
      />
    </div>
  );
}
```

### 🎯 Props Best Practices

1. **Always use descriptive prop names**
```javascript
// ❌ Bad
<UserCard n="John" a={25} />

// ✅ Good
<UserCard name="John" age={25} />
```

2. **Provide default values**
```javascript
function Button({ text = "Click me", color = "blue" }) {
  return (
    <button style={{backgroundColor: color}}>
      {text}
    </button>
  );
}
```

3. **Props are read-only**
```javascript
function Greeting({ name }) {
  // ❌ Never do this
  name = "Different name";
  
  // ✅ Props should not be modified
  return <h1>Hello, {name}!</h1>;
}
```

---

## 3. Introduction to State

### 🔄 What is State?

**State** is data that can change over time. When state changes, React automatically re-renders the component.

### 🏠 Real-World Analogy

Think of state like a light switch:
- **Current state:** On or Off
- **When you flip it:** State changes
- **Result:** The light updates automatically

### 📝 Using useState Hook

```javascript
import { useState } from 'react';

function Counter() {
  // useState returns [currentValue, setterFunction]
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>
        Increment
      </button>
    </div>
  );
}
```

### 🔍 Breaking Down useState

```javascript
import { useState } from 'react';

function Example() {
  // useState(initialValue) returns an array with 2 elements:
  // [currentStateValue, functionToUpdateState]
  const [count, setCount] = useState(0);
  
  // This is equivalent to:
  // const stateArray = useState(0);
  // const count = stateArray[0];
  // const setCount = stateArray[1];
  
  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```

### 🎯 Different Types of State

#### 1. Number State
```javascript
function Counter() {
  const [count, setCount] = useState(0);
  
  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>+</button>
      <button onClick={() => setCount(count - 1)}>-</button>
      <button onClick={() => setCount(0)}>Reset</button>
    </div>
  );
}
```

#### 2. String State
```javascript
function NameInput() {
  const [name, setName] = useState('');
  
  return (
    <div>
      <input 
        type="text" 
        value={name}
        onChange={(e) => setName(e.target.value)}
        placeholder="Enter your name"
      />
      <p>Hello, {name || 'Guest'}!</p>
    </div>
  );
}
```

#### 3. Boolean State
```javascript
function ToggleSwitch() {
  const [isOn, setIsOn] = useState(false);
  
  return (
    <div>
      <h2>Light is {isOn ? 'ON' : 'OFF'}</h2>
      <button onClick={() => setIsOn(!isOn)}>
        Toggle
      </button>
      <div style={{
        width: '100px',
        height: '100px',
        backgroundColor: isOn ? 'yellow' : 'gray',
        borderRadius: '50%'
      }} />
    </div>
  );
}
```

#### 4. Array State
```javascript
function TodoList() {
  const [todos, setTodos] = useState(['Learn React', 'Build an app']);
  const [newTodo, setNewTodo] = useState('');
  
  const addTodo = () => {
    if (newTodo.trim()) {
      setTodos([...todos, newTodo]);
      setNewTodo('');
    }
  };
  
  return (
    <div>
      <input 
        value={newTodo}
        onChange={(e) => setNewTodo(e.target.value)}
        placeholder="Add new todo"
      />
      <button onClick={addTodo}>Add</button>
      <ul>
        {todos.map((todo, index) => (
          <li key={index}>{todo}</li>
        ))}
      </ul>
    </div>
  );
}
```

### 🛠️ Exercise 5: Color Picker

Create a component that changes background color:

```javascript
import { useState } from 'react';

function ColorPicker() {
  const [selectedColor, setSelectedColor] = useState('white');
  
  const colors = ['red', 'blue', 'green', 'yellow', 'purple', 'orange'];
  
  return (
    <div style={{
      backgroundColor: selectedColor,
      padding: '20px',
      borderRadius: '10px',
      textAlign: 'center'
    }}>
      <h2>Color Picker</h2>
      <p>Selected: {selectedColor}</p>
      <div>
        {colors.map(color => (
          <button
            key={color}
            onClick={() => setSelectedColor(color)}
            style={{
              backgroundColor: color,
              color: 'white',
              margin: '5px',
              padding: '10px',
              border: 'none',
              borderRadius: '5px',
              cursor: 'pointer'
            }}
          >
            {color}
          </button>
        ))}
      </div>
    </div>
  );
}
```

---

## 4. Event Handling

### 🖱️ What are Events?

Events are actions that happen in your app - clicking buttons, typing in inputs, hovering over elements, etc.

### 📝 Basic Event Handling

```javascript
function ButtonExample() {
  const handleClick = () => {
    alert('Button was clicked!');
  };
  
  return (
    <button onClick={handleClick}>
      Click me!
    </button>
  );
}
```

### 🎯 Common Event Types

#### 1. Click Events
```javascript
function ClickEvents() {
  return (
    <div>
      <button onClick={() => console.log('Button clicked')}>
        Console Log
      </button>
      
      <button onClick={() => alert('Hello!')}>
        Alert
      </button>
      
      <button onClick={(e) => {
        console.log('Event object:', e);
        console.log('Button text:', e.target.textContent);
      }}>
        Event Details
      </button>
    </div>
  );
}
```

#### 2. Input Events
```javascript
function InputEvents() {
  const [inputValue, setInputValue] = useState('');
  
  return (
    <div>
      <input 
        type="text"
        value={inputValue}
        onChange={(e) => setInputValue(e.target.value)}
        onFocus={() => console.log('Input focused')}
        onBlur={() => console.log('Input blurred')}
      />
      <p>You typed: {inputValue}</p>
    </div>
  );
}
```

#### 3. Form Events
```javascript
function FormExample() {
  const [formData, setFormData] = useState({
    name: '',
    email: ''
  });
  
  const handleSubmit = (e) => {
    e.preventDefault(); // Prevent page refresh
    console.log('Form submitted:', formData);
  };
  
  const handleChange = (e) => {
    setFormData({
      ...formData,
      [e.target.name]: e.target.value
    });
  };
  
  return (
    <form onSubmit={handleSubmit}>
      <input 
        name="name"
        value={formData.name}
        onChange={handleChange}
        placeholder="Name"
      />
      <input 
        name="email"
        value={formData.email}
        onChange={handleChange}
        placeholder="Email"
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

### 🛠️ Exercise 6: Interactive Counter

Create a counter with multiple operations:

```javascript
import { useState } from 'react';

function InteractiveCounter() {
  const [count, setCount] = useState(0);
  const [step, setStep] = useState(1);
  
  
