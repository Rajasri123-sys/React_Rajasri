# React_Rajasri

React is a JavaScript library for building user interfaces.
React is used to build single-page applications.
React allows us to create reusable UI components.

import { createRoot } from 'react-dom/client';
function Hello() {
  return (
    <h1>Hello World!</h1>
  );
}
createRoot(document.getElementById('root')).render(
  <Hello />
);

Before you continue you should have a basic understanding of the following:
HTML
CSS
JavaScript

React is a front-end JavaScript library.
React was developed by the Facebook Software Engineer Jordan Walke.
React is also known as React.js or ReactJS.
React is a tool for building UI components.

React creates a VIRTUAL DOM in memory.
Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.
React only changes what needs to be changed!
React finds out what changes have been made, and changes only what needs to be changed.
You will learn the various aspects of how React does this in the rest of this tutorial.

Setting up a React Environment
First, make sure you have Node.js installed. You can check by running this in your terminal:

node -v
If Node.js is installed, you will get a result with the version number:

v22.15.0
If not, you will need to install Node.js.

Install a Build Tool (Vite)
When you have Node.js installed, you can start creating a React application by choosing a build tool.

We will use the Vite build tool in this tutorial.

Run this command to install Vite:

npm install -g create-vite
If the installation was a success, you will get a result like this:

added 1 package in 649ms
Create a React Application
Run this command to create a React application named my-react-app:

npm create vite@latest my-react-app -- --template react
If you get this message, just press y and press Enter to continue:

Need to install the following packages:
create-vite@6.5.0
Ok to proceed? (y)
If the creation was a success, you will get a result like this:


> npx
> create-vite my-react-app --template react

|
o  Scaffolding project in C:\Users\stale\my-react-app...
|
—  Done. Now run:

  cd my-react-app
  npm install
  npm run dev
Install Dependencies
As the result above suggests, navigate to your new react application directory:

cd my-react-app
And run this command to install dependencies:

npm install
Which will result in this:

added 154 packages, and audited 155 packages in 8s

33 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
Run the React Application
Now you are ready to run your first real React application!

Run this command to run the React application my-react-app:

npm run dev
Which will result in this:

VITE v6.3.5  ready in 217 ms

➜ Local: http://localhost:5173/
➜ Network: use --host to expose
➜ press h + enter to show help
A new browser window will pop up with your newly created React App! If not, open your browser and type localhost:5173 in the address bar.

Look in the my-react-app directory, and you will find a src folder. Inside the src folder there is a file called App.js, open it and it will look like this:

ExampleGet your own React.js Server
This is the default content of the App.jsx file in the src folder:

App.jsx
import { useState } from 'react'
import reactLogo from './assets/react.svg'
import viteLogo from '/vite.svg'
import './App.css'

function App() {
  const [count, setCount] = useState(0)

  return (
    <>
      <div>
        <a href="https://vitejs.dev" target="_blank">
          <img src={viteLogo} className="logo" alt="Vite logo" />
        </a>
        <a href="https://react.dev" target="_blank">
          <img src={reactLogo} className="logo react" alt="React logo" />
        </a>
      </div>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.jsx</code> and save to test HMR
        </p>
      </div>
      <p className="read-the-docs">
        Click on the Vite and React logos to learn more
      </p>
    </>
  )
}

export default App
Try replacing the entire file content with the code below and save the file.

Example
Replace all the content of the App.jsx file with the code below:

App.jsx
function App() {
  return (
    <div className="App">
      <h1>Hello World!</h1>
    </div>
  );
}

export default App;
See the changes in the browser when you click Save.

Notice that the changes are visible immediately after you save the file, you do not have to reload the browser!

React renders HTML to the web page via a container, and a function called createRoot().

The Container
React uses a container to render HTML in a web page.

Typically, this container is a <div id="root"></div> element in the index.html file.

If you have followed the steps in the previous chapter, you should have a file called index.html in the root directory of your project:

ExampleGet your own React.js Server
The default content of the index.html file:

index.html
<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + React</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
To better understand the content of the index.html file, let's remove all the code we don't need.

Example
The index.html file should now look like this:

index.html
<!doctype html>
<html lang="en">
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>
The file is now stripped from unnecessary code, and we can concentrate on learning React without any disturbing elements.

The createRoot Function
The createRoot function is located in the main.jsx file in the src folder, and is a built-in function that is used to create a root node for a React application.

Example
The default content of the src/main.jsx file:

main.jsx
import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'

createRoot(document.getElementById('root')).render(
  <StrictMode>
      <App />
    </StrictMode>
  )  
The createRoot() function takes one argument, an HTML element.

The purpose of the function is to define the HTML element where a React component should be displayed.

To better understand the createRoot function, let's remove unnecessary code and write our own "Hello React!" example:

Example
The src/main.jsx file should now look like this:

main.jsx
import { createRoot } from 'react-dom/client'

createRoot(document.getElementById('root')).render(
  <h1>Hello React!</h1>
)

The render Method
Did you notice the render method?
The render method defines what to render in the HTML container.
The result is displayed in the <div id="root"> element.

Example
Display a paragraph inside the "root" element:

main.jsx
import { createRoot } from 'react-dom/client'

createRoot(document.getElementById('root')).render(
  <p>Welcome!</p>
) 

Show React
W3Schools has its own "Show React" tool where we will show the result of the code we explain in the tutorial.
Click the "Run Example" button to see the result:
Example
The same example shown in our "Show React" tool:

main.jsx
import { createRoot } from 'react-dom/client'

createRoot(document.getElementById('root')).render(
  <p>Welcome!</p>
) 

The HTML Code
The HTML code in this tutorial uses JSX which allows you to write HTML tags inside the JavaScript code:
Don't worry if the syntax is unfamiliar, you will learn more about JSX later in this tutorial.
Example
Create a variable that contains HTML code and display it in the "root" node:

main.jsx
import { createRoot } from 'react-dom/client'

const myelement = (
  <table>
    <tr>
      <th>Name</th>
    </tr>
    <tr>
      <td>John</td>
    </tr>
    <tr>
      <td>Elsa</td>
    </tr>
  </table>
);

createRoot(document.getElementById('root')).render(
  myelement
)

The Root Node
The root node is the HTML element where you want to display the result.
It is like a container for content, managed by React.
It does NOT have to be a <div> element and it does NOT have to have the id='root':

Example
The root node can be called whatever you like.
Display the result in the <header id="sandy"> element:

index.htmlmain.jsx
<!doctype html>
<html lang="en">
  <body>
    <header id="sandy"></header>
    <script type="module" src="/src/main.jsx"></script>
  </body>
</html>

Classes
ES6 introduced classes.
A class is a type of function, but instead of using the keyword function to initiate it, we use the keyword class, and the properties are assigned inside a constructor() method.
ExampleGet your own React.js Server
A simple class constructor:

class Car {
  constructor(name) {
    this.brand = name;
  }
}
 The constructor function is called automatically when the object is initialized.

 Method in Classes
You can add your own methods in a class:
Example
Create a method named "present":

class Car {
  constructor(name) {
    this.brand = name;
  }
  
  present() {
    return 'I have a ' + this.brand;
  }
}
const mycar = new Car("Ford");
mycar.present();

Class Inheritance
To create a class inheritance, use the extends keyword.
A class created with a class inheritance inherits all the methods from another class:
Example
Create a class named "Model" which will inherit the methods from the "Car" class:

class Car {
  constructor(name) {
    this.brand = name;
  }

  present() {
    return 'I have a ' + this.brand;
  }
}
class Model extends Car {
  constructor(name, mod) {
    super(name);
    this.model = mod;
  }  
  show() {
      return this.present() + ', it is a ' + this.model
  }
}
const mycar = new Model("Ford", "Mustang");
mycar.show();

The super() method refers to the parent class.
By calling the super() method in the constructor method, we call the parent's constructor method and get access to the parent's properties and methods.

