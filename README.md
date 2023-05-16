# React.js-Learnings
Notes / Documentation of stuff i have learned<br>

**what is a component**<br>
small reusable code that could be used later. example : header and footer can be component , as it could be used on multiple pages.

**what is single page application**<br>
only single page is there and everything is there stored in the same page as components , So when we need to display lets say login page we simply load that component associated with login page.

**why React**<br>
single page application<br>
its flexible<br>
Reusability thru components and properties<br>
Strong and Big React community<br>

### Starting out with React


**when coding on vscode**<br>
install ES7 react... extension , material icon extension , auto import extension<br>
also goto settings search for emmet include language , then include --> javascript : javascriptreact( its a key value pair)

**starting out with react**<br>
open termial at the desired folder and write
```
npx create-react-app name_of_your_app
```
this will load all the basic files required for creating react application Inside the folder name_of_your_app.
side note : npx means related to executing , npm means realted to managing hence an 'm'

need to write this for starting out with you new app
```
cd name_of_your_app
npm start
```
 
some commands to be remembered
```
npm start #starts development server
npm run build # bundles app files for production
npm test #starts the test runner
```

**understanding this create-react-app code structure**<br>
you have 3 folders in total
1) node_modules : you skip this out when uploading your project on github , .gitignore helps you with it.
2) public : contains your index.html , inside index .html you have a div element with id="root" , this is where all your react code will be poured.<br>
3) src : this is where all your react code is present
4) inside scr you have index.js file where all the react code is present , directly or indirectly(thru components).
package.json file contains info about package dependencies and other dependencies.
```
now , how react works is that although you don't have a single line of code in index.html but react.js converts all the code written in scr to bundle.js and when index.html runs on browser it gets the code from bundle.js
```


**boilerplate code of react-js**<br>

1. here you simply write "./app" because app.js is in the same folder hence ./ to go back then app is the name of file and you don't need to write .js because it's understandable.<br>
2. afer importing app.js as App , to call this component you need to form an anchor of App itself hence , <App/>

index.js<br>
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/3e6a6b58-d7e4-4e80-89b9-4e621b23af29)

app.js<br>
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/8fdd75b3-19f2-4a37-86c7-4b7647dcc036)


**what is component based architecture in react**<br>

In React, a component-based architecture refers to the practice of building applications by breaking them down into reusable, self-contained building blocks called components. Each component encapsulates a specific piece of functionality or user interface element and can be composed and combined to create more complex user interfaces.<br>

Components in React are written as JavaScript classes or functions that return JSX (JavaScript XML) code. <br>They can have their own state, receive input through props (properties), and can render UI elements to the DOM.<br>

**what is rendering in react js**<br>

In simple words , rendering in React refers to the process of taking the instructions that make up a component and turning them into actual web page elements that the user can see and interact with.

Technically , Rendering in React refers to the process of generating a view of a component hierarchy in response to changes in its state or props. When a React component is rendered, it returns a tree of React elements (usually written using JSX) that represent the UI that should be displayed to the user.

React uses a process called reconciliation to determine how to update the view efficiently. It compares the current state of the component hierarchy with the previous state, and determines which parts of the DOM need to be updated to reflect any changes.

**what are states in react**

Think of state in React as a container that holds important information for a component. It's like a box that can store data and values that might change over time.

**<needs to be updated **
 
