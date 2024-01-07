`Written by James Plummer with Obsidian.md + backed up to GitHub via Git plug-in.`

## Table of contents

### 0. Preface

### 1. Introduction
Data types, basic arithmetic operators, variables and basic projects.
### 2. Conditionals
If, if...else, else statements, comparison operators, logical operators, truthy and falsy, ternary operators and more basic projects.
### 3. Functions

### 4. Scope

### 5. Arrays



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
(Note: there are more differences than what are mentioned above, they will be discussed later. For now, this is enough information.)

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

(Note: === checks that the data types of the values are matching. == also works otherwise.)

Basic examples:
```JS
10 < 12 // Evaluates to true

'apples' === 'oranges' // false
```

Practical example:
```JS
let hungerLevel = 7;

if (hungerLevel => 7){ // if hungerLevel is greater than or equal to 7 -> 'Time to eat!'
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

It's also possible to return the value of a function inside another function. These functions being called within another function are often called helper functions. Each function carries out a specific task which makes code easier to read and debug if necessary. It allows us to break down larger more difficult tasks into smaller more manageable tasks.

Let's look at an example of a helper function in action:
```JS
function multiplyNineOverFive(number) {  // step 3
  return number * (9/5);  
};  
  
function getFahrenheit(celsius) {  // step 2
  return multiplyNineOverFive(celsius) + 32;  // step 4
};  
  
getFahrenheit(15); // step 1
```
We can see that the function `getFahrenheit(15)` was called with the argument `15` for the `celcius` parameter in this case. 

The code block inside `getFahrenheit()` calls `multiplyNineOverFive(15)` with the argument `15`. In this case, we can see that the `15` was used as an argument for `celcius` and now  `celcius` is being used as an argument for `multiplyNineOverFive()` replacing the `number` parameter with the argument `15`.

Now that we can see the original call with argument `15` -> `celcius` parameter as argument -> `number` parameter as argument, it's easier to understand.  We can see that the code block for `multiplyNineOverFive(15)` = 15 * (9/5) which evaluates to 27. 27 is then returned back to the function call `getFahrenheit()` which simply adds 32 which finally returns 59 to the original function call. So 15 degrees C = 59 degrees F.

To summarise: 

`getFahrenheit(15)` -> `multiplyNineOverFive(15)` -> returns 27 to `getFahrenheit(15)` -> 32 is added to complete the function call.

This is a difficult topic to explain in words. I added comments to the example above to try and help. I will probably improve this section in the future.

---

### Function Expressions

Another way to define a function is by using a function expression. To define a function inside an expression we still use the `function` keyword however, in a function expression the function name is usually removed - this is known as an anonymous function. Instead they can be stored in a variable so it can be referred to as a normal function.

Let's take a look at an example:
```JS
const funcVariable = function(day) {
	if (day === 'Monday') {
		return true;
	} else {
		return false;
		}
}
console.log(funcVariable('Tuesday'); // prints false
```
The easiest way to think of this is by comparing it to a normal function call. Here is an identical situation with a normal function.
```JS
function funcVariable(day) {
	if (day === 'Monday') {
		return true;
	} else {
		return false;
		}
}
console.log(funcVariable('Tuesday'); // prints false
```
The only difference is how we declare the variable (and also that we can make them anon)
```JS
// function expression
const funcVariable = function(day) {
};
// standard function declaration
function funcVariable(day) {
};
```

According to my research, the main advantage of function expression is the fact that they are stored in a `const` constant variable that can not be changed. This may be appropriate when dealing with larger scripts and collaborative projects? Not sure, need to read more but it appears to a better practice than standard function declaration. Possibly due to the fact that they aren't hoisted so they can not be called until they are defined unlike normally declared functions.

---

### Arrow Functions

ES6 also marked the release of arrow function syntax which gives us a shorter way to write functions by using the "fat arrow" notation `() =>`. This removes the need to type `function` every time you need to create a function. They are written in a similar way to function expressions.

Instead, the parameters are included in `()` before the `=>` that points to the function body `{}`. I'll add various examples below:
```JS
// arrow function
const arrowFunction = (parameter1, parameter2) => {
};
// function expression
const functionExpression = function(parameter1, parameter2) {
};
// normal function declaration
function normalFunction(parameter1, parameter2) {
}
```
Notice how arrow functions and function expressions are anonymous. As mentioned before, an anonymous function has no name but, it can still be assigned to a variable. With a normal function declaration, anonymous functions are not possible.

It's good to be familiar with the different ways functions can be written. As mentioned before, based on my brief research, arrow functions and function expressions appear to be the best way forward.

---

### Concise Body Arrow Functions

Now we'll discuss some more niche points about arrow functions. JavaScript provides several ways to refactor arrow function syntax. The most condensed form is known as concise body.

Depending on the number of parameters needed for a function, we can adjust how it is written to make it more concise.
```JS
// 0 parameters
const functionName = () => {};
// 1 parameter
const functionName = parameter1 => {};
// 2 or more parameters
const functionName = (parameter1, parameter2) => {};
```
So, let's outline the differences:

| Parameters | Changes |
| ---- | ---- |
| 0 | `()` still required |
| 1 | `()` not required |
| 2+ | `()` still required |

This is only the beginning of refactoring functions too... Now let's take a look at something called an implicit return. If a function block only needs a single line we can remove the curly brackets `{}` and make use of an implicit return to remove the `return` keyword. For example:
```JS
const total = (number) => {
	return number + number;
};
```
Can be adjusted to this based on it's parameter count (1):
```JS
const total = number => {
	return number + number;
};
```
Which can now be adjusted to this with an implicit return:
```JS
const total = num => num + num;
```
We can remove the `return` keyword and without the curly brackets `{}` on a single line block, whatever the line evaluates to will be automatically returned. The contents of the block should immediately follow the `=>`.

---

### Project 5 - Rock, Paper, or Scissors

```JS
// rock paper scissors (change userInput variable on line 7)

console.log('Hello James.');

// Function to get the user's choice
const getUserChoice = userInput => {
  userInput = 'paper';
  userInput = userInput.toLowerCase();
  if ((userInput === 'rock') || (userInput === 'paper') || (userInput === 'scissors')) {
    return userInput;
  } else {
    return 'Accepted inputs are: "rock", "paper" or "scissors".';
  }
};
let userChoice = getUserChoice();
console.log(`You choose ${userChoice}.`);


// function to get computer's choice
function getComputerChoice() {
  // Generate random integer between 0-2.
  let computerChoice = Math.floor(Math.random() * 3);
  // Computer's choice based on random number
  switch (computerChoice) {
    case 0:
      return 'rock';
    case 1:
      return 'paper';
    case 2:
      return 'scissors';
    default:
      return 'An error has occurred.';
  }
}
let computerChoice = getComputerChoice();
console.log(`Computer chooses ${computerChoice}.`);


// Function to determine the winner between user and computer
function determineWinner(userChoice, computerChoice) {
  // Checks if it's a tie
  if (userChoice === computerChoice) {
    return 'It\'s a tie...';

  } else if (
    // winning scenarios for user
    (userChoice === 'rock' && computerChoice === 'scissors') ||
    (userChoice === 'paper' && computerChoice === 'rock') ||
    (userChoice === 'scissors' && computerChoice === 'paper')
  ) {
    return 'You win!';
  } else {
    return 'Computer wins!';
  }
}
// prints result of determineWinner function
console.log(determineWinner(userChoice, computerChoice));
```

### Project 6 - Sleep Debt Calculator

```JS
// Function to get the sleep hours for each day
function getSleepHours(day) {
  switch (day.toLowerCase()) {
    case 'monday':
      return 7;
    case 'tuesday':
      return 8;
    case 'wednesday':
      return 8;
    case 'thursday':
      return 8;
    case 'friday':
      return 8;
    case 'saturday':
      return 8;
    case 'sunday':
      return 8;
    default:
      return 'error';
  }
};

// Function to calculate the total actual sleep hours for the week
function getActualSleepHours() {
  return (
    getSleepHours('monday') +
    getSleepHours('tuesday') +
    getSleepHours('wednesday') +
    getSleepHours('thursday') +
    getSleepHours('friday') +
    getSleepHours('saturday') +
    getSleepHours('sunday')
  );
};

// Function to calculate the ideal sleep hours for the week based on a given daily ideal hours
function getIdealSleepHours(idealHours) {
  return idealHours * 7;
}

// Function to compare actual and ideal sleep hours and provide feedback
function calculateSleepDebt() {
  let actualSleepHours = getActualSleepHours();
  let idealSleepHours = getIdealSleepHours(8); // Assuming 8 hours ideal sleep per night
  // Compare actual and ideal sleep hours and provide feedback
  if (actualSleepHours === idealSleepHours) {
    console.log("You're sleeping the perfect amount!");
  } else if (actualSleepHours > idealSleepHours) {
    console.log(
      `You're sleeping ${actualSleepHours - idealSleepHours} hour(s) more than needed.`
    );
  } else {
    console.log(
      `You're sleeping ${idealSleepHours - actualSleepHours} hour(s) less than needed.`
    );
  }
}

// Calculate and display sleep debt information
calculateSleepDebt();
```

---
---

## Scope

Scope defines where variables can be accessed or referenced. Some variables can be accessed throughout an entire program, others may only be available in a specific context.

First of all, we need to understand what a block is. We've seen blocks used in functions and if statements. A block is the code that can be found within curly brackets `{}`. They serve as an important structural marker for our code.

Let's look at a quick example:
```JS
if (colour) {
	let colour = 'yellow';
	console.log(colour); // prints 'yellow' because colour = true
}
```

---

### Global Scope

We think about scope in relation to blocks because variables can exist within or outside of blocks. In global scope, variables are declared outside of blocks which makes them accessible throughout the entire program.

For example:
```JS
const myFavColour = 'red'; // global scope variable (outside function block)

const returnFavColour = () => { // arrow function assigned to variable returnFavColour
	return myFavColour; // 'red'
}

console.log(returnFavColour()); // prints 'red'
```

---

### Block Scope

Variables defined inside a code block are only accessible to the code within the `{}`. This is called block scope or local scope.

For example:
```JS
const logFavColour = () => {
	let colour = 'red';
	console.log(colour); // prints 'red'
};
logFavColour(); // prints 'red' because the arrow function variable has global scope
console.log(colour); // throws ReferenceError because colour has block scope
```

---

### Scope Pollution

At first sight, it may appear to be a good idea to have all variables accessible globally. However, too many globally assigned variables can cause problems in a program. When a global variable is declared, it goes to the global namespace which allows them to be accessed anywhere in a program. The variables remain in the global namespace until the program is finished which means our global namespace can fill up really quickly. 

Scope pollution is when we have too many global variables that exist in our global namespace or when we reuse variables across different scopes. This can make it difficult to keep track of our different variables and can lead to accidents e.g. when globally scope variables collide with other variables which cause unexpected behaviour in our code. 

For example:
```JS
let number = 50; // variable number declared and given value of 50

const logNumber = () => {
	number = 100; // number variable is now reassigned to 100
	console.log(number); // reassigned number is printed
};

logNumber(); // prints 100
console.log(number); // also prints 100 but we've now unknowingly changed the global variables value
```

---

### Practicing Good Scoping

As we've seen previously with the issues we faced with globally scoped variables, we should now have a better understanding as to why tighter scoped variables are best practice. Some reasons:

- Makes code easier to read because it is organized into more discrete sections via blocks.
- Makes the code more understandable because we can see which variables are associated with which parts of the program.
- Easier to maintain due to the discrete sections (more modular).
- Saves memory in code because the global namespace isn't polluted and the variables cease to exist after the code block finishes running.

A good example from Codecademy:
```JS
const logVisibleLightWaves = () => {

  let lightWaves = 'Moonlight';
  let region = 'The Arctic';
  
  if (region === 'The Arctic'){
    let lightWaves = 'Northern Lights';
    console.log(lightWaves); // exists within the block so we can print 'Northern Lights'
  }
  console.log(lightWaves); // exists OUTSIDE the block so we can print 'Moonlight' with the same variable name because it is still within the function block but outside the if statement
};

  

logVisibleLightWaves(); // prints 'Northern Lights' AND 'Moonlight'
```

---

### Project 7 - Training Days

```JS
const name = "Nala"; // globally scoped variable 'name'

// function to produce random number and return event name based on number
const getRandEvent = () => { // globally scoped variable used for function
  const random = Math.floor(Math.random() * 3); // locally scoped variable 'random'
  if (random === 0) {
    return "Marathon";
  } else if (random === 1) {
    return "Triathlon";
  } else if (random === 2) {
    return "Pentathlon";
  }
};

// function to determine number of days to train based on event argument
const getTrainingDays = (event) => {
  let days; // locally scoped variable 'day'
  if (event === "Marathon") {
    days = 50;
  } else if (event === "Triathlon") {
    days = 100;
  } else if (event === "Pentathlon") {
    days = 200;
  }

  return days;
};

// globally scoped variable with function that takes 2 arguments 'name', 'event' and prints string with their info
const logEvent = (name, event) => { 
  console.log(`${name}'s event is: ${event}`);
};

// globally scope variable with function that takes 2 arguments 'name', 'day' and prints string with their info
const logTime = (name, days) => {
  console.log(`${name}'s time to train is: ${days} days`);
};

// globally scope variables that call functions
const event = getRandEvent();
const days = getTrainingDays(event); // calls function with argument 'event'

logEvent(name, event); // calls logEvent function with name ('Nala') and event (from function getRandEvent())
logTime(name, days); // calls logTime function with name ('Nala') and days (from getTrainingDays(event) function)

// here we can assign new global variables for a different person and use the same functions for them to determine their personal training days information
const event2 = getRandEvent();
const days2 = getTrainingDays(event2);
const name2 = "Warren";

// these perform the same tasks as above but with different variables
logEvent(name2, event2);
logTime(name2, days2);
```

---
---

## Arrays

Arrays are an important part of programming. They allow us to organize and store data.

For example, a shopping list for 1. eggs, 2. milk and 3. butter could be written as an array like this:
```JS
let shoppingList = ['eggs', 'milk', 'butter'];
```
As you can see, arrays are stored in `[]` and elements (items) in the list are separated by `,`. Arrays can store any data type (such as strings, numbers and booleans). Like a list, arrays are ordered meaning each element has a numbered position. Unlike lists in real life, arrays start at a position of 0, meaning the first element in an array is position 0, the second element is position 1 etc.

Here is an example of an array containing elements with different data types:
```JS
let diffDataTypes = ['string', 1, true];
```

Let's see what happens when we clog an array:
```JS
let holidayLocations = ['Paris', 'Rome', 'Stockholm'];

console.log(holidayLocations);
```
The code above will print "['Paris', 'Rome', 'Stockholm']" to the console, exactly as it is written in the array.

---
### Accessing Elements

Each element in an array has a numbered position known as it's index. We can access individual items by using their index which is similar to our shopping list earlier where item 1. was eggs. The key difference here is that arrays in JavaScript are zero-indexed, meaning the positions start at 0 not 1. Let's look at a couple of examples:
```JS
let words = ['mouse', 'keyboard', 'monitor']; 

console.log(words[1]); // prints position 1 so 'keyboard' to the console
```

Here's another way we can use index - to access individual characters in a string:
```JS
const name = 'James Plummer';

console.log(name[4]); // prints character position 4 so 's' to the console
```

---
### Updating Elements

Now we understand how to access elements, we can update them. Like this:
```JS
let words = ['mouse', 'keyboard', 'monitor'];

words[2] = 'imposter';
console.log(words);
console.log(words[2]);
```
Here we updated the 2nd element so 'monitor' to now be 'imposter'. When we clog it, it will output "['mouse', 'keyboard', 'imposter']". If we clog the 2nd position of words, it will output "imposter".

---
### Arrays with let and const

As we discussed in the variables section earlier, we can declare with both `let` and `const` keywords. Variables declared with `let` can be reassigned. Variables declared with the `const` keyword can not be reassigned. However, elements in an array declared with `const` remain mutable, meaning that we can change the contents of a `const` array but we can not reassign a new array or a different value.

Let's take a look at an example from Codecademy:
```JS
// array that can be assigned a new array or a different value
let condiments = ['Ketchup', 'Mustard', 'Soy Sauce', 'Sriracha'];
// array that can not be assigned a new array or a different value
const utensils = ['Fork', 'Knife', 'Chopsticks', 'Spork'];

condiments[0] = 'Mayo'; // reassigns position 0 of condiments to = 'Mayo'
console.log(condiments); // clogs ['Mayo', 'Mustard', 'Soy Sauce', 'Sriracha']

condiments = ['Mayo']; // assigns new array to condiments - only contains 1 element now
console.log(condiments); // clogs ['Mayo']

utensils[3] = 'Spoon'; // reassigns position 3 of utensils to = 'Spoon'
console.log(utensils); // clogs ['Fork', 'Knife', 'Chopsticks', 'Spoon']

utensils = ['Spoon']; // gives us a "TypeError: Assignment to constant variable." because we tried to give the variable a new array
```

---
### The .length property

Arrays have a built-in property in JS which returns the number of items in an array. It is called `length` and can be access by chaining the property to the name of the array using `.` dot notation. Here is an example:
```JS
const objectives = ['Learn JS', 'Master JS', 'Become JS GOD'];

console.log(objectives.length); // clogs 3 because objectives length is 3 elements
```

---
### The .push() method

There are also built-in methods that make working with arrays easier. These methods are specifically called on arrays to make common tasks like adding or removing elements easier. One method known as `.push()` allows us to add items to the end of an array. Here is an example:
```JS
const myItems = ['item 0', 'item 1', 'item 2'];  

myItems.push('item 3', 'item 4');  
  
console.log(myItems);  
// Output: ['item 0', 'item 1', 'item 2', 'item 3', 'item 4'];
```
In the same way as for the `.length` property, we use dot notation to connect `push` to `myItems`. Then we can call it like a function - `.push()` is a built in function that can be used directly on an array. Here we are giving it 2 arguments 'item 3' and 'item 4' but it can take multiple arguments, here we only want to add 2 elements.

`.push()` changes or mutates `myItem`. You may also see `.push()` referred to as a destructive array method since it changes the initial array.

---
### The .pop() method

Another method we can use is `.pop()` which removes the last item of an array. For example:
```JS
const myItems = ['item 0', 'item 1', 'item 2'];  
  
const removedItem = myItems.pop(); // declare new variable = popped element
  
console.log(myItems); 
// Output: [ 'item 0', 'item 1' ]  
console.log(removedItem); 
// Output: item 2
```
`.pop()` does not take any arguments like `.push()` did previously. It can only remove the last element of an array. Here we are using it to remove the last element from `myItems` and store it in the variable `removedItem`. Like `.push()`, `.pop()` is a method that mutates the initial array.

--- 
### More Array Methods

There are many other array methods. A full list can be found in MDN and Codecademy docs. Below I'll mention a few others and some basic examples:

`.shift()` removes the first element from an array thus shifting the following elements down one place. It takes no arguments.
```JS
const groceries = ['orange juice', 'bananas', 'coffee beans', 'rice', 'pasta', 'olive oil', 'salmon'];

groceries.shift(); // In this case 'orange juice' is removed
console.log(groceries); // output: ['bananas', 'coffee beans', 'rice', 'pasta', 'olive oil', 'salmon']
```

`.unshift` adds an element to the beginning of an array. It takes arguments that are the items we want to add to the beginning of the array.
```JS
const groceries = ['orange juice', 'bananas', 'coffee beans', 'rice', 'pasta', 'olive oil', 'salmon'];

groceries.unshift('popcorn'); // In this case 'popcorn' is added to the beginning
console.log(groceries); // output: ['popcorn', 'bananas', 'coffee beans', 'rice', 'pasta', 'olive oil', 'salmon']
```

`.slice()` is used to create a shallow copy of part or all of an array without modifying the original array. A shallow copy duplicates the contents of an object into a new instance by reference which is why changes to the copy are not reflected in the original. It can take two arguments, the first states the first element to return, the second states up to and including which element to return. For example, `.slice(0, 4)` would return every element from position 0 up to and including 4. If a 2nd argument isn't provided, the start element and all following elements will be returned. Here's an actual example:
```JS
const weekDays = ['Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday'];

const outOutOffice = weekDays.slice(1, 4); // starts pos 1, ends and includes pos 4

console.log(outOutOffice); // clogs the new sliced array
// Output: ['Tuesday', 'Wednesday', 'Thursday']
```

---
### Arrays and Functions

Throughout the 'Arrays' section of these notes, we discussed how arrays are mutable or changeable. Now we need to understand what happens if we try to change an array within a function. Will the array be changed after the function is called or is it scoped within the function? Let's take a look at an example from Codecademy:
```JS
const flowers = ['peony', 'daffodil', 'marigold'];  
  
function addFlower(arr) {  // here we have a function with a parameter 'arr'
  arr.push('lily');  // whatever array is used as an argument for the parameter 'arr' will have the string "lily" pushed to it - remember that .push() mutates an array by adding an element to the end of it
}  
  
addFlower(flowers);  // here we call the function with the argument of the 'flowers' array

// based on the function body, we can see that it pushes "lily" to the array that is given as an argument
  
console.log(flowers); // Output: ['peony', 'daffodil', 'marigold', 'lily'] 
```
Above, we can see that the array was mutated within a function but, the array remains mutated outside the function as well. This concept can be called a "pass-by reference" since what we're actually doing is passing the function a reference to where the variable memory is stored and changing the memory contents.

--- 

### Nested Arrays

Arrays can store other arrays. This is known as a nested array and can look something like this:
```JS
const nestedEx = [[1],[2, 3]];

console.log(nestedEx[1]); // Output [2, 3]
```
`[2, 3]` is stored at index position 1 in the array. If we want to access elements in a nested array, we can chain together more bracket notations with index values:
```JS
const nestedEx = [[1], [2, 3]];  
  
console.log(nestedEx[1]); // Output: [2, 3]  
console.log(nestedEx[1][0]); // Output: 2
```
On line 4, you can see we first index on the 'outer' array, position 1 and then called position 0 on the nested 'inner' array which gave us an output of 2 because it is the 1st element in the nested array. Remember that indexing begins at 0 so index 0 is the first element.

---

### Project 8 - Secret Message

```JS
// Secret message array containing words
let secretMessage = ['Learning', 'is', 'not', 'about', 'what', 'you', 'get', 'easily', 'the', 'first', 'time,', 'it', 'is', 'about', 'what', 'you', 'can', 'figure', 'out.', '-2015,', 'Chris', 'Pine,', 'Learn', 'JavaScript'];

// Remove the last entity from the array
secretMessage.pop();

// Add two entities ('to' and 'Program') to the end of the array
secretMessage.push('to', 'Program');

// Change the array entity at index 7 to 'right'
secretMessage[7] = 'right';

// Remove the first entity from the array
secretMessage.shift();

// Add 'Programming' to the beginning of the array
secretMessage.unshift('Programming');

// Replace a portion of the array (from index 6 to index 10) with 'from'
secretMessage.splice(6, 5, 'from');

// Display the secret message by joining the array elements with a space
console.log(`Secret message = ${secretMessage.join(' ')}`);

// Display the length of the array
console.log(`Array length = ${secretMessage.length}`);
```

---
---
## Loops

A loop is an extremely common and useful programming tool that allows our program to repeat a set of instructions until a condition is met, known as a stopping condition. Please note that the word 'iterate' will be used frequently when discussing loops but, it basically just means "to repeat".

When we need to reuse a task in our code, we often bundle the action into a function. When we can see that a process needs to be run multiple times, we create a loop - they allow us to write efficient code.

For a real world example: If you are hungry, you eat until you reach the stopping condition, which is when you are full and no longer want to eat. 

Let's look at a simple example so we can better understand just how useful loops are:
```JS
vacationSpots = ['Italy', 'Finland', 'Bali'];

console.log(vacationSpots[0]); // output: Italy
console.log(vacationSpots[1]); // output: Finland
console.log(vacationSpots[2]); // output: Bali
```
In the case above, it's quite simple because the array is small but imagine if there were 100 elements - it would be extremely tedious and inefficient, this is where a loop can help us.

---
### For Loops

A typical `for` loop contains an iterator variable which usually appears in all 3 expressions in the loop. Typically, this is how a `for` loop works: 
1. The iterator variable is initialized;
2. It is checked against a stopping condition; 
3. Then it is assigned a new value on each loop iteration.

Here's an example which I'll explain below:
```JS
for (let counter = 5; counter < 9; counter++){

  console.log(counter);
}
/* Output:
5
6
7
8
*/
```
1. The initialization is `let counter = 5` so the counting will begin at 5;
2. The stopping condition is `counter < 9` so the counter will run as long as the iterator variable `counter` is less than 9.
3. The iteration statement is `counter++` which means for each loop, the value of `counter` will increase by 1. First iteration will be 5, second will be 6 etc.

The code block within the `{}` will run until the condition evaluates false, so when `counter >= 9`.

We can do the exact same thing in reverse, like this:
```JS
for (let counter = 9; counter >= 5; counter--){
	console.log(counter);
}
/* Output:
9
8
7
6
5
```
1. The initialization is `let counter = 9` so the counting will begin at 9;
2. The stopping condition is `counter >= 5` so the counter will run as long as the iterator variable `counter` is greater than or equal to 5.
3. The iteration statement is `counter--` which means for each loop, the value of `counter` will decrease by 1. First iteration will be 9, second will be 8 etc.

The code block within the `{}` will run until the condition evaluates false, so when `counter < 5`.

---
### Looping through Arrays

`for` loops are very useful for iterating over data structures. For example, we can use a `for` loop to perform the same operation on each element of an array. Imagine we owned a store and wanted to increase the price of all our products - this would be time consuming as it would require code for each product. Instead we can use a `for` loop to iterate through the array of products.

To loop through each element of an array, a `for` loop should use the array's `.length` property in it's condition, we have used this property previously. Let's take a look at an example and how it works:
```JS
const vacationSpots = ['Bali', 'Paris', 'Rovaniemi'];

for (let i = 0; i < vacationSpots.length; i++){

  console.log(`I would love to visit ${vacationSpots[i]}`);
}
/* Output:
I would love to visit Bali
I would love to visit Paris
I would love to visit Rome */
```
So, first we need an array, in this case we used a `const` variable with the name `vacationSpots` which contains the elements `Bali`, `Paris` and `Rovaniemi` to form an array.

Now let's take a look at how the 2nd part functions. As usual, we start the for loop with `for` and there are the 3 expressions as we discussed previously. However, now it looks a little different:

1. `let i = 0;` - here we are initializing our iterator variable using the name `i`, short for index, instead of `counter` like we had earlier. This functions in exactly the same way, we start the index at position 0 (the first position) of the array, in this case.
2. `i < vacationSpots.length` - here is the stopping condition, so the loop will keep iterating as lothe iterator variable `i` is less than the length of the array `vacationSpots` which is 3.
