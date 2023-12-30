`Written by James Plummer with Obsidian.md + backed up to GitHub via Git plug-in.`

## Table of contents

### 0. Preface

### 1. Introduction

Data types, basic arithmetic operators, variables and basic projects.
### 2. Conditionals

If, if...else, else statements, comparison operators, logical operators, truthy and falsy, ternary operators and more basic projects.
## 3. Functions



---
---
## 0. Preface

From the beginning, I am aware it is very noob-y but I want to document information down to the finest details. Later I can summarize and eventually I will not need this document other than for reference. For now, enjoy noob level information :)

---
---
## 1. Introduction

7 Fundamental data types in JS:

| Type | Example |
| ---- | ---- |
| Strings | `Hello` |
| Numbers | `1` |
| Booleans | `true` |
| Undefined | `undefined` |
| Symbol | `%` |
| Object | need good example |

Built-in arithmetic operators:

| Symbol | Function | Example/info |
| ---- | ---- | ---- |
| + | addition | a + b |
| - | subtraction | a - b |
| * | multiplication | a * b |
| / | division | a / b |
| % | remainder | Divides by x and returns what remains e.g. 10 % 3 = 3 remainder 1<br>so 10 % 3 = 1 |

Objects can have properties, methods and store information. Properties are denoted by appending the object or instance with a full-stop + property name e.g.
```JS 
// prints length of string
console.log('hello'.length);
```

Methods can perform actions. Methods are called by appending the object or instance with a full-stop + method name + brackets e.g.
```JS
// prints string in uppercase
console.log('hello'.toUpperCase());
```

Built in objects such as `Math` are collections of methods and properties that JS provides.

Remember case sensitivity. 
```JS
variableName != VariableName
```
---
### Variables

```JS
var = preES6VariableName
const = constantVariable
let = variableThatCanBeChanged
```

Variables that have not be initialised store the primitive data type `undefined`.

In ES6 we can use backticks and `${}` to interpolate values into a string - known as 'template literals'. We can also use basic string concatenation too.
```JS
let userName = 'James';
// prints string 'Hello, James.'
console.log(`Hello, ${userName}.`); // template literals - more concise

console.log('Hello, ' + userName + '.'); // string concatenation - better compatibility
```

We can use `typeof` keyword to return data type as a string.
```JS
const int = 1;
const string = 'Hello';
const bool = true;
// in order: number, boolean, string
console.log(`"Number" is a ${typeof int}.
"True or false" is a ${typeof bool}.
"Word" is a ${typeof string}.`);
```

---
### Project 1 - Kelvin Weather

```JS
// sets a constant variable that states todays forecast is 293K
const kelvin = 100;
// sets a variable that converts Kelvin to Celcius
let celcius = kelvin - 273;
// converts celcius temp fahrenheit using conversion equation
let fahrenheit = Math.floor(celcius * (9/5) + 32);
// converts celcius to newton using conversion equation
let newton = Math.floor(celcius * (33/100));

console.log(`The temperature is:

${fahrenheit} degrees Fahrenheit.

${celcius} degrees Celcius.

${kelvin} degrees Kelvin.

${newton} degrees ?Newton?.

Please note: All values are rounded down to the nearest whole number.`);
```
---
### Project 2 - Dog Years

```JS
/* variable set to my age
let myAge = 22;
// variable for early dog years. first 2 years dog = 2 * 10.5 human years
let earlyYears = 2 * 10.5;
// accounted for 2 years so we remove it from age
let laterYears = myAge - 2;
// times 4 to account for later years
laterYears *= 4;
*/
// Improved version:
let laterYears = (myAge - 2) * 4;
// addition of above calculations show my age in dog years
let myAgeDogYears = laterYears + earlyYears;
// built in method to make my name uppercase
myName = "jAmEs".toUpperCase();

// string interpolation to display sentence about name and ages
console.log(`My name is ${myName}. I am ${myAge} years old in human years which is ${myAgeDogYears} years old in dog years.`);
```

---
---
## 2. Conditionals

Conditional statements check condition(s) and perform a task based on them. Below we will discuss a variety of types.

### If , Else...if and Else Statements

```JS
if (true) {
console.log('This message will print!`);
} else if (false) {
console.log('Now this one will print!');
} else {
console.log('If all else fails... this will print');
}
```

### Comparison Operators

To compare values we can use different types of operators. Below is a list of some useful comparison operators and their syntax.

| Operator | Syntax |
| ---- | ---- |
| Less than | < |
| Greater than | > |
| Less than or equal to | <= |
| Greater than or equal to | >= |
| Is equal to | === |
| Is not equal to | !== |

(Note: === also checks to the data types of the values are matching. == also works otherwise.)

Basic examples:
```JS
10 < 12 // Evaluates to true

'apples' === 'oranges' // false
```

Practical example:
```JS
let hungerLevel = 7;

if (hungerLevel => 7){
  console.log('Time to eat!');
} else {
  console.log('We can eat later!');
}
```

---
### Logical Operators

| Operator | Syntax | Notes |
| ---- | ---- | ---- |
| AND | `&&` | Both conditions must evaluate to `true` for the entire condition to evaluate to `true`. |
| OR | \|\| | Only 1 condition must evaluate to `true`. If it's the 1st condition, the 2nd will not be even be checked. |
| NOT (bang) | `!` | Reverses or negates the boolean value. Basically makes `true` -> `false` or <br>`false` -> `true`. |

Examples for each are provided below:

AND (`&&`)
```JS
let mood = 'happy';
let happinessLevel = 9;

// BOTH conditions must be met for 'yippee'.
if (mood === 'happy' && happinessLevel > 9) {
	console.log('yippee');
} else { 
	console.log('no yippee :(');
}
```

OR ( || )
```JS
if (day === 'saturday' || day === 'sunday') {
	console.log("It's the weekend!");
} else {
	console.log('Weekday... Bruh...');
}

/* Notice above I was able to deal with the apostrophe in "It's" by using double quotes " " instead of ' '.

This can also be done with a well-placed forward-slash / but " " is easier overall.
*/
```

NOT/bang (`!`)
```JS
let test = true;
// prints the opposite of test's boolean value - so false.
console.log(!test);
```

---
### Truthy and Falsy

This is how we can check if a variable has been assigned a value.
```JS
const number = 1;
console.log(number); // evaluates to true

const number; // here you can see the variable is declared but isn't assigned a value
console.log(number); // evaluates to false (undefined)
// It would also be false if it was given the value 0 - see below.
```

The same also applies to other data types, not just numbers. Here is a list of falsy values:

| Details | Example |
| ---- | ---- |
| Integer | `0` |
| Empty string | `""` or `''` |
| no value at all | `null` |
| declared variable lacks a value | `undefined` |
| Not a Number | `NaN` |

---
### Ternary Operator

(Note: Only compatible with ES6, I believe - need to verify.)

Ternary operators are used to simplify if...else statements. Example below:

Normal if statement:
```JS
let verify = true;

if (verify) {
	console.log('It is true');
} else {
	console.log ('It is false');
}
```

Ternary operator for the same example:
```JS
verify ? console.log('It is true') : console.log('It is false');
```

In the example above, the condition `verify` is provided before the `?`. Following the question mark there is a `true` expression + `:` + `false` expression.

If the condition evaluates to `true`, the first expression executes. If the condition evaluates to `false`, the second expression executes.

As you can see, ternary operators are significantly more efficient and offer shorter-handed syntax. Although, they can only be used if the needed expression is either `true` or `false`.

---
### Switch Statements

A switch statement is another way in which we can shorten our code. It is also easier to read and write for us. Let's look at an example below:

Normal if else statement:
```JS
let food = 'papaya';  
  
if (food === 'banana') {  
  console.log('Bananas are $0.49');  
} else if (groceryItem === 'papaya'){  
  console.log('Papayas are $1.29');  
} else {  
  console.log('Invalid item');  
}
```

Switch statement for the same example:
```JS
let food = 'papaya';  
  
switch (food) {  
  case 'banana':  
    console.log('Bananas are $0.49');  
    break;  
  case 'lemon':  
    console.log('Lemons are $1.49');  
    break;  
  case 'papaya':  
    console.log('Papayas are $1.29');  
    break;  
  default:  
    console.log('Invalid item');  
    break;  
}
```

The output in both cases is the same: "Papayas are $1.29".

Now let's take a look at how each section of the switch statement works compared to the if...else statement.

| Part of statement | Explanation |
| ---- | ---- |
| `switch` keyword | Initiates the statement and is followed by `()` which contains the value that each case will be compared to. In our case this is the variable `'food'` which contains the string 'papayas'. |
| The main block - between the `{}`. | This is where we place our `case`s. |
| `case`s | `case`s are what we use to check if a condition is met by the expression that follows. For example, 'papayas' match in our case so 'Papayas are $1.29' would log to the console. |
| `break` | Once a `case` is `true` we need to exit the code block so it doesn't continue running after the condition was satisfied. We only include `break` after the condition has been met and the necessary action has been taken. E.g. we matched 'papaya' and logged to console THEN `break`. |
| `default` | In cases, instead of `else`, we use `default`. This is a fallback in case no condition is met. It is essential to include a `default` case. |

Take note of the syntax here. For example, the conditions in an if statement are enclosed in `()` but, in switch statements, each case is followed by `:` and there are no `()` for each individual condition (`case`).

---

### Project 3 - Magic Eight Ball

```JS
let userName = 'James';
let userQuestion = 'Will it rain today?';
let randomNumber = Math.floor((Math.random() * 8) + 1);
let eightBall = '';

// ternary operator to say hello with/without userName
userName ? console.log(`Hello, ${userName}!`) :
console.log('Hello!');

// confirms question with string concatenation + with/without userName
userName ? console.log(`Here is an answer to your question "${userQuestion}", ${userName}`) :
console.log(`Here is an answer to your question "${userQuestion}"`);

//switch statement to assign string to eightBall based on randomNumber
switch (randomNumber) {
  case 1:
    eightBall = 'It is certain';
    break;
  case 2:
    eightBall = 'It is highly likely';
    break;
  case 3:
    eightBall = 'It is quite likely';
    break;
  case 4:
    eightBall = 'It is slightly likely';
    break;
  case 5:
    eightBall = 'It is slightly unlikely';
    break;
  case 6:
    eightBall = 'It is quite unlikely';
    break;
  case 7:
    eightBall = 'It is highly unlikely';
    break;
  case 8:
    eightBall = 'It is impossible';
    break;
  default:
    eightBall = 'Invalid';
    break;
}

// final output from eightBall to answer question
console.log(`${eightBall}`);
```

---
### Project 4 - Race Day

```JS
let raceNumber = Math.floor(Math.random() * 1000);
let earlyRunner = false;
let runnerAge = 18;

if (runnerAge > 18 && earlyRunner){
  raceNumber += 1000;
}

if (runnerAge > 18 && earlyRunner){
  console.log(`You will race at 9:30 AM. Your race number is: ${raceNumber}`);
  
} else if (runnerAge > 18 && !earlyRunner){
  console.log(`You will race at 11:00 AM. Your race number is: ${raceNumber}`)

} else if (runnerAge < 18){
  console.log(`You will race at 12:30 PM. Your race number is: ${raceNumber}`)

} else {
  console.log('Please visit the registration desk.');
}
```

---
---
## Functions

When programming, we often need to complete a specific task or set of tasks multiple times.  A block of code can be group under a single function that can be called like so `function()`. This allows us to group a sequence of tasks under a single entity. This way our code will be clearer and more concise.

For example, the code below could be place in a function. Otherwise, we need to type the entire block if we need to calculate the area of 3 rectangles.
```JS
const width = 10;  
const height = 6;  
const area =  width * height;  
console.log(area);
```

---
### Function Declarations

There are 3 parts to a function declaration:
- `function` keyword
- The name of the function or it's identifier followed by brackets `()`
- The body of the function which can contain a block of statements to perform a specific task. The function body is enclosed within `{}`

Once a function is declared, we can call it. It will complete the task from the function body.

Here is an example:
```JS
function sayHello(){ // declare the function and give it a name
  console.log('Hello World!'); // function body enclosed within {}
}

sayHello(); // call the function and it will output 'Hello World!'
sayHello(); // we can do it as many times as we want
```

---
### Parameters and Arguments

So far, we've only looked at functions without an input. However, some functions can take inputs and use them to perform a task. For this, we need to specify the functions parameters. The parameters for a function are enclosed within the functions `()` when it is declared and separated by a `,`

Here is an example:
```JS
function userInfo(name, age) { // declared function and set parameters name and age
	console.log('Your name is ' + name + '. You are ' + age + ' years old.');
}
userInfo(James, 22); // here we call the function but with arguments, see below
// output 'Your name is James. You are 22 years old.'
userInfo(Bob, 38); // here we call it again but with different arguments
// output 'Your name is Bob. You are 38 years old.'
```
(Note, if the `+ name +` and `+ age +` is confusing, please revisit the variables section where string concatenation and template literals were discussed.)

Once we have a function declared with parameters, we can then give arguments to the function when calling it so the function can use this data. In my example, we used the input (argument) of `James` for the `name` parameter and `22` as the input (argument) for `age`.

---
### Default Parameters

One new feature added in ES6 is the ability to use default parameters. This allows us to set a predetermined value for a parameter if an argument isn't given.

Let's look at an example:
```JS
// below the function is declared and default parameters are given for item1, 2 and 3.
function shoppingList(item1 = 'milk', item2 = 'bread', item3 = 'eggs'){
  console.log(`Remember to buy ${item1}`);
  console.log(`Remember to buy ${item2}`);
  console.log(`Remember to buy ${item3}`);
}
shoppingList();
```
This will output:
`'Remember to buy milk'`
`'Remember to buy bread'`
`'Remember to buy eggs'`

But we can still give it arguments and overwrite the defaults, like this:
```JS
function shoppingList(item1 = 'milk', item2 = 'bread', item3 = 'eggs'){
  console.log(`Remember to buy ${item1}`);
  console.log(`Remember to buy ${item2}`);
  console.log(`Remember to buy ${item3}`);
}
shoppingList('popcorn', 'fruit', 'cheese'); // Arguments will overwrite the defaults
```
This will be the new output:
`'Remember to buy popcorn'`
`'Remember to buy fruit'`
`'Remember to buy cheese'`

Imagine a case where you have a new user on your site. You don't know their name yet so you can't use it as an argument. Instead, you can have a default parameter like `stranger`.

---
### Return

When a function is called, the computer will run through the function's code and evaluate a result. By default, the resulting value is `undefined`.

Let's take a look at an example to understand how the keyword `return` works:
```JS
function rectangleArea(width, height) {  
  let area = width * height;  
}  
console.log(rectangleArea(5, 10))
```
When the code above runs, the console log prints `undefined`. The code works and the computer calculates the area to be '50' but we didn't capture this information so it couldn't be passed back to the function.

To do this we need a return statement, like this:
```JS
function rectangleArea(width, height) {  
  let area = width * height;  
  return area;
}  
console.log(rectangleArea(5, 10))
```
Now the information will be passed back to the function and our output to the console will be '50'.

It's important to note that a `return` statement stops the execution of the function and any code that follows won't be executed. This can be powerful in cases like this:
```JS
rectangleArea(width, height) {  
  if (width < 0 || height < 0) {  
    return 'Positive numbers are needed to calculate area! Please try again.';  
  }  
  return width * height;  
}
```
Here we check if the width and height entered are positive, if they are not we `return` an error message and do not output the area. If the numbers are positive, the if statement is false so it is skipped and we `return` the area (`width * height`).

---

### Helper Functions

