# Written Homework week 19 day 03

## What are all the JavaScript Data Types?
* Array
* Object
* Number
* Bigint
* String
* Boolean
* Symbol
* Undefined
* Null

## What is the Difference Between Const Let and Var? Consider Scope ... Give an example
### Var
Variables defined with var can be redelcared

Var can be globally and locally scoped

Var, however, is problematic for the reason shown in the example below:

``` 
var greeter = "hey hi";
var times = 4;

    if (times > 3) {
        var greeter = "say Hello instead"; 
    }
    
console.log(greeter) // "say Hello instead"
```

Above you can see the variable `tester` greeter has been redeclared inside the if statement. This issue here is that you could redefine greeter without knowingly doing so. For this reason, Let was created.

### Let
Unlike var, let cannot be redeclared within the same scope. They must also be declared before use. Let variables are defined as having block scope.

```
let greeting = "say Hi";
let greeting = "say Hello instead"; // error: Identifier 'greeting' has already been declared
```
If let is defined within differen scopes, then they are treated as totally different variables. 

```
let greeting = "say Hi";

    if (true) {
        let greeting = "say Hello instead";
        console.log(greeting); // "say Hello instead"
    }

console.log(greeting); // "say Hi
```
### Const
Const variables cannot be redeclared and reassigned. Like let, they also have block scope.

```
const PI = 3.141592653589793;
PI = 3.14;      // This will give an error
PI = PI + 10;   // This will also give an error
```

## Pass By Value vs Pass By Reference? Why would you say a String is pass by value/ or a value type? Why is an object a reference type?

## What do Map , Filter and Reduce do? Do they mutate the array you call them on?
## What are all the Falsey Values in JavaScript? Why do you think this is important to know?
## What are Async and Await?
## What is an async function?
## What are try and catch?

### Resources
[JS Datatypes](https://www.w3schools.com/js/js_datatypes.asp)

[Var Let & Const](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)

[Let](https://www.w3schools.com/js/js_let.asp)