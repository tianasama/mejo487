# Functions
In programming, being able to reuse different data is one of the most basic necessities. Functions allow us to do just that. Think of them as many programs inside the main program that can be invoked at any time.

The syntax to declare a function is:

```
function doSomething() {
  // do stuff...
}

//This invokes or call the function
doSomething();
```

## Example
If we want to create a simple way to multiply numbers, we could create separate variables and then call them like so.

```js runnable
// let's multiply 8 by 2
var a =  8 * 2;

// now let's multiply 12 by 2
var b = 12 * 2;

// now let's multiply 4 by 2
var c =  4 * 2;

console.log(a);
console.log(b);
console.log(c);
```

However, instead of rewriting the operation multiple times, we can write a function once and then use it with different numbers.

```js runnable
function multiply(num) {
  return num * 2;
}

console.log(multiply(8));
console.log(multiply(12));
console.log(multiply(4));
```


## Declaring a Function

![Function Declaration Diagram](https://tiy-learn-content.s3.amazonaws.com/ded51be5-js-function-2.jpg)


## Calling a Function

While declaring a function makes it available for use, the code inside the function body won't actually run until you **call** the function.

```js runnable
// a function declaration
function square(x) {
  return x * 2;
}

// calling that same function:
console.log(square(4));
```


## Function Body and the `return` Keyword

Inside of the function body, you can do as much work as you need. You can declare variables, use operators, even declare and use other functions. Once you're done, use the `return` keyword to specify what data your function call will return.  Observe:

```js runnable
function addAndDouble(num1, num2) {
  var addNums = num1 + num2;
  var total = addNums * 2;
  return total;
}

console.log(addAndDouble(35, 45));
```

## Parameters and Arguments
Parameters are variables that are only accessible inside the function. Arguments are the real values passed to (and received by) the function.

JavaScript functions can accept more than one parameter (or none at all). The order of the arguments will relate directly to the order of the parameters.

```js runnable

//a,b,c are the parameters
function announceParams(a, b, c){
  console.log("Parameter a is " + a);
  console.log("Parameter b is " + b);
  console.log("Parameter c is " + c);
}

/// root beer, 24, 3.40 are the arguments
announceParams("root beer", 24, "$3.40");
```

## Objects inside functions
Objects can hold arrays and can be passed into functions.

```js runnable
var moseyTheDog = {
  age: 3,
  furColor: 'brindle',
  likes: ['frisbee', 'ball']
}

function describeDog(dog) {
  var description = 'This dog is ' + dog.age + ' years old with ' + dog.furColor + ' fur and likes to play ' + dog.likes[1];
  return description;
}

console.log(describeDog(moseyTheDog));
```

# Scope
Scope is the concept of what's visible and invisible at certain parts of the program—what the program can see (variables, functions). It's all about visibility.

- Global Scope: Things that are visible everywhere in the program are said to live in the "Global Scope." They usually appear at the top of the page.
- Local Scope: A variable declared inside of a function has a local scope and can only be seen within that function.

```js runnable
var global = "global variables"; //global scope

// we can use the gloval var anywhere!

// inside a function
function globalScope() {
  console.log(global + " inside function");
}

globalScope();

//outside a function
console.log(global + " outside function");
```

```js runnable
// here is a function that has a local var
function localScope() {
   var local = "local variables";
   console.log(local + " works just fine inside a function");    
}

localScope();

// But what happens when we try to call a locally scoped variable outside of the function?
console.log(local + " does not work here");
```
