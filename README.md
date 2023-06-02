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

**what are props**
props are shorthand for properties , these are immutable in nature and can't be changed.

**what is JSX**
JSX (JavaScript XML) is a syntax extension used in React that allows you to write HTML-like code within JavaScript.
```
const name = "John";
const element = <h1>Hello, {name}!</h1>;
```

There are some rules related to javascript.<br>

When writing JSX in React, there are a few rules to keep in mind to ensure that your code is valid and properly interpreted by the React compiler. Here are three important rules for writing JSX:

1. Use Proper Tag Closure:
   Every JSX element must be properly closed, either with a closing tag or a self-closing tag. For example, `<div>Hello</div>` is a properly closed `<div>` element, while `<input />` is a self-closing `<input>` element. Make sure to include the closing slash in self-closing tags.

2. Use JavaScript Expressions in Curly Braces:
   To embed JavaScript expressions or variables within JSX, enclose them in curly braces `{}`. For example, `<h1>Hello, {name}!</h1>` allows you to insert the value of the `name` variable into the JSX output. You can include any valid JavaScript expression within the curly braces.

3. Use a Single Root Element:
   JSX expressions must have a single root element. This means that you should wrap multiple elements within a single parent element. For example, instead of writing:
   ```jsx
   <h1>Hello</h1>
   <p>Paragraph</p>
   ```
   You should wrap them in a parent element like this:
   ```jsx
   <div>
     <h1>Hello</h1>
     <p>Paragraph</p>
   </div>
   ```
   If you don't want to introduce an additional parent element, you can use a fragment (`<>...</>`) or React.Fragment to wrap the elements without adding a new DOM node.
   
   
**props in react**<br>

when you want to pass information from one component to other we use props , you can pass the info as parameters example:

<Header text1="dash dash" text2="blah blah" />
here the react functional component will have 2 props , which u can access by props.text1 , props.text2.

note: when you have dynamic value then don't pass the value as it is instead use {} so for example <Header tasklist={task} />

### User Input , Events and UseRef

side note: when you write html code inside javascript you mostly write arr.map(()=>( <p>  </p> ) ) basically ()=>() instead of ()=>{} , you can write ()=> {} but here you would have to write ()=>{return( html_code )} .<br>

this is what we want to create

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/07f29a16-91ef-441c-bf0b-1d5eb5283293)


remember : event.target.value

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/b54e417c-0af9-4c3e-8303-7561e4ec9e30)

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/4214a69d-5a1f-4de0-8e28-3ab4045b0093)

notice onClick (can be used for button as well as elements) , onChange(used for input fields mostly)<br>
now after reseting the taskValue , although the taskValue state would have changed but it won't be reflected in the input field for that write `<input value={taskValue} ...>`
<br>
 
lets add one more field <br>
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/fd71a896-87b4-45cc-81fe-e1c28e858eea)

**handling Submit button**

handling submit button is a bit tricky as it redirects to GET url for example : localhost://3000?task=abc etc.<br>
so for no page redirection write : event.preventDefault();

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/353494a2-56e0-4c5b-8ae8-14702d9723e2)


so this is what we are returning :
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/54e89224-2271-4420-b071-e8d0be41c375)

### UseRef Hook

So , total 2 things:<br>
i)its just like useState but in useState the whole component re-renders after state changes but this doesn't happen with useRef.<br>
ii) used to access DOM elements directly so instead of using getElementbyId etc. you can simply use this as well , just need to use ref={useRefObjectName};<br>
<br>
also in first point note that its not like you won't see updated value of useRef object , so whenever redering happens due to lets say change of some different state then while the rerendering , you would see updated value of useRef object. useRef object has a property current that stores the value.<br>

DOM manupulation example:
```
  const inputRef = useRef(null);

  function handleClick() {
    inputRef.current.focus();
    console.log(inputRef.current.value);
  }

  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleClick}>
        Focus the input
      </button>
    </>
  );
  ```
  
  

**JSON-Server(used for testing application with help of json server , which acts as fake api and outputs json file**


<br>
read how to use it , by going thru readme file.<br>

https://github.com/typicode/json-server
<br>
to install it globally:<br>
```npm install -g json-server```


use this command to change the port as default port is 3000 which react also uses hence would give error.<br>
```
json-server --watch db.json --port 3004
```

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/f0554b92-e517-4491-88e6-936c77cfed99)

<br>
note: do not do this as this will be an infinite loop (setProduct is a state change func)

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/3640cd10-bf70-4a3e-8d53-7e7f43f6dfb8)

<br>
if you want to make it run once , you need to use useEffect because it runs only once or when a state changes.
<br>

**UseEffect**

useEffect runs once when passed [] empty array as second argument , and will be called when [dependency] state is changed .

ReactStrict mode : when in development phase we use ReactStrict mode which renders every element twice hence when in production remove the strict mode of react.
<br>




## React Router

you need to import {browserRouter} from react-router-dom library , and close this around <App/> , this needs to be done in index.js
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/c3b1651f-819a-4d11-920b-6c17e86c9273)


then to create routes you need to import {routes,route} and do this in app.js :
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/701b5015-3611-4f6a-b3e1-add9c17c8f48)


**Difference between a_tag , link element , navlink element**
<br>
a_tag will simply open a new page , hence full page will get refreshed instead use link or navlink tags from react-router library<br>

note that the difference between navlink and react is that navlink adds active class to the link that matches with the selected link , so for example if selected link= /products then the links that matches this are / and /products so both of them will have class = active too , but if you want exact match then write 'end' at the end. Also you need to define .active css property in css file other wise no visual changes would be there.

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/d1078f98-2be2-4ade-b2e8-bd5b57b206d6)

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/074d6bad-4b6e-40ad-bff1-beb7c7947d49)

notice instead of href='' we are using to='/products'

### useNavigate hook and Navigate element

useNavigate is used to redirct to a particular route . Here's an example
![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/c6f2af5b-fccd-426d-992b-8855da51cbde)

Navigate element is used as , but first import navigate from react-router-dom library:

![image](https://github.com/ritikagr061/React.js-Learnings/assets/54122273/27d4edce-bc19-4e1f-866f-d87bb799c085)



