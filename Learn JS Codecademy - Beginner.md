
hello this is an example testing more testing

```JS

let variable = 'cheese';

console.log('Hello');
```

## Introduction

7 Fundamental data types in JS:
- Strings
- Numbers
- Booleans (true/false)
- Undefined
- Symbol
- Object

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


