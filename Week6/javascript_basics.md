# Constructors
The constructor property returns a reference to the Object constructor function that created the instance object. 
A constructor is any function which is used as a constructor. The language doesn’t make a distinction. A function can be written to be used as a constructor or to be called as a normal function, or to be used either way. A constructor is used with the new keyword. 

# Functions
* Function creates a new function object (an object that can be invoked).
* You must include parenthesis when invoking a function. This is to communicate to the JavaScript interpreter that we want it to execute this function, as opposed to returning the function itself.
* You can declare arguments in functions
* You must explicitly use return if you want to return a value from JS
* There are no classes in JS but we do use functions as a convenient way to instantiate objects that share behaviour (objects in JS are just bags of properties.(ES5. ES6 has introuduced class functionality.)


# Prototype
A function is just a special kind of object, and like any object a function can have properties. Functions automatically get a property called prototype, which is just an empty object. This object gets some special treatment.
It's important to understand that unlike Ruby where your instances inherit from a class, when it comes to JavaScript, your instances inherit from another object. But for now, we can think of prototype as a "storage area" which relates to the object referenced immediately before the prototype keyword and stores the function (method) you are defining.
(ES5)

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

