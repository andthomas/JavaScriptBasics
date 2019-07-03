
# Javascript Foundations

I've created this document to bring together what I believe to be the most important concepts for developing a foundational knowledge of JavaScript. It is not an exhaustive guide but is reasonably detailed. Initially you can use this to gain a high level understanding of JavaScript, then come back to it as a point of reference as you encounter JS in the wild.

So let's dig in.

## What is JavaScript?
JavaScript is a programming language that can run both in a browser and (more recently) on a server. It was written to run in the Netscape browser in 1995. JavaScript can update and change our HTML and CSS, calculate and manipulate data and request and receive data from servers or other websites. 

## Data types
Data types are a concept that are common across all programming languages. In JavaScript there are 7 primitive data types:

### 1. Strings

A string is a sequence of characters. A string literal is a sequence surrounded by either single or double quotes.

    ‘Stringy string string’ 
    “How’s ya bloody string mate”

A string literal can also be so-called template literals (introduced into JS in ES6) by using backticks.

    `Literally a template literal example`

### 2. Numbers

A number can be either a positive or negative integer or a positive or negative decimal (floating point number).

    1
    -13
    7.849
    -934.379

### 3. BigInt
Numbers can only get us so far. The largest number that JavaScript can reliably represent is 2^53. Anything larger than this we should handle with BigInt. Even so, BigInts can only be represented with arbitrary precision, meaning its precision is limited to the amount of memory that is available to our JavaScript code in our computer. 
A BigInt is created by adding an 'n' to the end of the integer.

    > 8923494n

### 4. Booleans
A boolean represents a value of `true` or `false`.

### 5. Null
`null` is just a special value which represents “nothing” or “empty”.

### 6. Undefined
Not to be confused with null, the meaning of `undefined` is “value is not assigned”.

### 7. Symbols
Symbols are new in the latest version of JavaScript (ES6). A symbol is a unique identifier whose value is its description. Two Symbols with the exact same description are not equal. Symbols are used when a completely unique value is needed. 
Sounds confusing? Well it bloody is and its a fairly advanced feature which we don't need to worry about right now.

    Symbol(uniqueNewYork)


## Variables and constants

A variable or constant consists of an identifier (to the left of the equals sign) and a value (to the right of the equals sign). Its value can be a primitive data type, an array, an object or a function. A variable or constant can be initialised with a value or with an undefined value.

    var newVar = "Hello, World!";
    var otherNewVar; //Initialised with an undefined value
    
### Let vs. Const. vs. Var
Pre ES6, we declared variables with the `var` keyword. With `var` we can set a variable to have some value then either manipulate it's value or assign it a new value.

    var greeting = "Hey there bucko";
    var greeting = "What's up dawg?";
    console.log(greeting);
    > "What's up dawg?"

ES6 introduced two new ways of declaring variables which have mostly replaced `var`. These are `const` and `let`. The keyword `const` initialises a constant, which, like a variable, is able to store the same kinds of information. However, unlike a variable, its value cannot be changed. In programming we say it is *immutable*. 

    const hey = 'ya';
    const hey = 'there';
    > Uncaught SyntaxError: Identifier 'hey' has already been declared

For now, we can safely assume `let` is the same as `var`. There is a slight difference in how it is *scoped*, a concept which we will explore in the section on functions. 

## Operators
JavaScript operators are used to assign values, compare values, perform arithmetic operations, and more.

### Assignment
As we saw before, we can assign a variable a value by using the `=` operator. This is by far the most commonly used operator. However, there are a number of assignment operators we can use in JavaScript. Two more of these operators are addition assignment `+=` and subtraction assignment `-=` which compound values while assigning them.

    let x = 3;
    x += 10;
    console.log(x);
    > 13
    
    x -= 5;
    console.log(x);
    > 8


### Comparison
Comparison operators compare two values and returns a boolean. JavaScript has two types of equals comparisons, equal and strict equal. Equals checks to see if the values are the same, irrespective of their types while strict equals compares value and type.

    10 === '10'
    > false
    10 === 10
    > true
    
    10 == '10'
    > true
    10 == 10
    > true

The not equal comparison operator `!=` and strict not equal comparison operator `!==` have the same approach to comparing types as their equals counterparts, but checks to see if values are not equal.

    6 !== 6
    > false
    6 !== '6'
    > true
     
    6 !== '6'
    > false
    6 !== 6
    > false
    
We can also compare two values using the greater than `>` and less than `<` operators.

    3 > 2
    > true
    17 < 62
    > false

### Arithmetic 

### Logical

    
## Truthy and falsey  


## Type coercion


## Functions

###  Scope and the ‘this’ keyword

## Conditionals

## Loops

## Math

## Methods
### String
### Array
### Object

## Events

## DOM manipulation