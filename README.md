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
var greet = "hello hey";
var num = 4;

    if (num > 3) {
        var greet = "say Hello There instead"; 
    }
    
console.log(greet) // "say Hello There instead"
```

Above you can see the variable `greet` has been redeclared inside the if statement. This issue here is that you could redefine greet without knowingly doing so. For this reason, Let was created.

### Let
Unlike var, let cannot be redeclared within the same scope. They must also be declared before use. Let variables are defined as having block scope.

```
let greet = "Hey There";
let greet = "say Hello There instead"; // error: Identifier 'greeting' has already been declared
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
const PI = 3.141592653589;
PI = 3.14;      // Will read an error
PI = PI + 17;   // Will also read an error
```

## Pass By Value vs Pass By Reference? Why would you say a String is pass by value/ or a value type? Why is an object a reference type?

### Pass by Value
Passing be value is used when describing `numbers` `booleans` `strings` `symbols` `null` and `undefined`.

These are considered pass by value because they are primitative data types. 

Example below:

```
// Primitives
const numb = 11;
const boolean = true;
const str = 'Hello!!';
const objectMissing = null;
const noValue = undefined;

```

When you pass by value means when you assign a value to `a` variable, a copy of the value will be created every time.

An example of this is below

```
let x = 3 //x --> 3
let y = x //y --> 3
```

This example shows that `y` is a crbon copy of `x`, but it doesnt affect `x` because it was declared only once.

### Pass by Reference
When passing by reference, you are given a refernce to that object in memory as an address. 

If you have assigned `a` variable to the same object referece, then changing the object will affect both variables

```
let a = [4] // a --> [4]
let b = a // b --> [4]
```

To write this further

```
let a = [4] 
let b = a 

b.push(3)

console.log(a) // [4, 3]
console.log(b) // [4, 3]
```

In the second code block above, an array is iniailized in the first line. The reference to that array is then assigned to a vaiable `a`.

`b` is then declared and then assigned to the object reference in `a`. This is called pass by reference.

The third line contains an item , 3, that is pushed into the array. Becuase both `a` and `b` are referencing the same array in memory, the push method will mutate the same array and will be reflected on both `a` and `b`.

## What do Map , Filter and Reduce do? Do they mutate the array you call them on?
### Map
When you want to create a mutated or transformed version of an original array, you can use `map()` method.

```
const nums = [2, 4, 6, 8]
cont half = nums.map(num => num / 2)

console.log(half) // [1, 2, 3, 4]
```
In the example above, the indiviual item in the array is selected and `num / 2` calculation is performed on the number and stored in a new array called `half`.


### Filter
The `filter()` method works by applying a conditional statement to individual elements in an array. If the statement returns true on the element, it will get pushed into a new array.

```
const nums = [1, 2, 3, 4];
const evens = numbs.filter(item => item % 2 === 0);

console.log(evens); // [2, 4]
```

The example above checks each itme in the array if there is no remainder after dividing by 2 (even numbers will be divisible by two without remainder).

### Reduce
The `reduce()` is used to take each element of an array and reduce the array contents down to just one element.

the reduce method is broken down as follows:

```
array.reduce(callback[, initialValue])
```
`callback` is a function used once for each element in the array. This function had the option of using 4 difference arguements, but normally only, `accumulator` (returning the value of the previous iteration) and `currentValue` (the element in the array that is currently selected).

```
const numbers = [2, 4, 6, 8];
const sum = numbers.reduce(function (total, element) {
  return total + element;
}, 0);

console.log(sum); // 20

```
In the example above, `total` is the accumulator and `element` is the current element in the array. It will loop through the whole array until a total accumulation has been reached.


## What are all the Falsey Values in JavaScript? Why do you think this is important to know?

* `false` - When using the keyword `false`
* `0` - This is the `number` `0` and any caculable variation that would lead to the number `0` (eg 0x0 = 0)
* `-0` - This is the same as above but when the number is a negative 
* `0n` - This is when `BigInt` doesn't have any value, or is `0n`.
* `""`, `''`, ` `` ` - When there is an empty string
* Boolean
* Symbol
* Undefined
* Null

## What are Async and Await?
## What is an async function?
## What are try and catch?

### Resources
[JS Datatypes](https://www.w3schools.com/js/js_datatypes.asp)

[Var Let & Const](https://www.freecodecamp.org/news/var-let-and-const-whats-the-difference/)

[Let](https://www.w3schools.com/js/js_let.asp)

[Pass by Value and Reference](https://dmitripavlutin.com/value-vs-reference-javascript/)

[Map, filter and reduce](https://www.freecodecamp.org/news/javascript-map-reduce-and-filter-explained-with-examples/)

[Falsey Values](https://developer.mozilla.org/en-US/docs/Glossary/Falsy)
