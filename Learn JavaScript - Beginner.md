`Written by James Plummer with Obsidian.md + backed up to GitHub via Git plug-in.`

## Table of contents

### 0. Preface
### 1. Introduction
### 2. Conditionals

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
| Object | `` |

Built-in arithmetic operators:

| Symbol | Function |
| ---- | ---- |
| + | addition |
| - | subtraction |
| * | multiplication |
| / | division |
| % | remainder |

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
variableName != VariableName.
```
---
### Variables

```JS
var = preES6VariableName
const = constantVariable
let = variableThatCanBeChanged
```

Variables that have not be initialised store the primitive data type `undefined`.

In ES6 we can use backticks and `${}` to interpolate values into a string e.g.
```JS
let userName = 'James';
// prints string 'Hello, James.'
console.log(`Hello, ${userName}.`);
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

Some basic examples:
```JS
10 < 12 // Evaluates to true

'apples' === 'oranges' // false
```

Useful example:
```JS
let hungerLevel = 7;

if (hungerLevel => 7){
  console.log('Time to eat!');
} else {
  console.log('We can eat later!');
}
```


