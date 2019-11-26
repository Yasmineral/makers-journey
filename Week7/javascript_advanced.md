# Console.dir
The Console method dir() displays an interactive list of the properties of the specified JavaScript object. The output is presented as a hierarchical listing with disclosure triangles that let you see the contents of child objects.

# Handlers
Event handlers are embedded in documents as attributes of HTML tags to which you assign JavaScript code to execute. The general syntax is. <TAG eventHandler="JavaScript Code"> where TAG is some HTML tag and eventHandler is the name of the event handler.
  
# Closures
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time. Consider the following:

```javascript
function init() {
  var name = 'Mozilla'; // name is a local variable created by init
  function displayName() { // displayName() is the inner function, a closure
    alert(name); // use variable declared in the parent function
  }
  displayName();
}
init();
```

init() creates a local variable called name and a function called displayName(). The displayName() function is an inner function that is defined inside init() and is only available within the body of the init() function. Note that the displayName() function has no local variables of its own. However, since inner functions have access to the variables of outer functions, displayName() can access the variable name declared in the parent function, init().

# Callback
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action. Here is a quick example:

```javascript
function greeting(name) {
  alert('Hello ' + name);
}

function processUserInput(callback) {
  var name = prompt('Please enter your name.');
  callback(name);
}

processUserInput(greeting);
```

The above example is a synchronous callback, as it is executed immediately.

Note, however, that callbacks are often used to continue code execution after an asynchronous operation has completed — these are called asynchronous callbacks. A good example is the callback functions executed inside a ```.then()``` block chained onto the end of a promise after that promise fulfills or rejects. This structure is used in many modern web APIs, such as ```fetch()```.

# Module pattern
A design pattern to encapsulate your JavaScript code. Uses iffy’s to wrap all the code and keep the details of creating the function private. This means none of the rest of the code can access any variables or functions inside the IIFE. The module pattern is basically an iffy, but it uses extra code to export (or show) functions and variables that are part of the public interface of the module, i.e we make available the function we want people to use, but hide some implementation details that we don't want to bother them with. We also prevent our hidden variables from clashing with variables in the rest of our program. 
Checkout the JS Module pill.

# Immediately Invoked Function Expression
(IFFE / ‘iffy’)
We use IIFEs to hide variable and function declarations. The important part is achieving the goal of encapsulation. Helps guard against hidden variable names clashing with variables in the rest of your program.

Keywords this and exports are the global object. This means that adding exclaim onto exports is effectively making exclaim globally available. That's why we can call exclaim("hi”).’ 

**The Window Object**  The window binding refers to a built-in object provided by the browser. It represents the browser window that contains the document. All global JS objects / functions / variables automatically become members of the window objet.

**The Document Object Model (DOM)** is a programming interface for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

**let** allows you to declare variables that are limited to a scope of a block statement, or expression on which it is used, unlike the var keyword, which defines a variable globally, or locally to an entire function regardless of block scope. The other difference between var and let is that the latter is initialized to value only when parser evaluates it. 
