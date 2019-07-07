
# Javascript Foundations

I've created this guide to bring together what I believe to be the most important concepts for developing a foundational knowledge of JavaScript. It is not a exhaustive but is reasonably detailed. Initially you can use this to gain a high level understanding of JavaScript, then come back to it as a point of reference as you encounter JS in the wild.

Examples will look like this:

    // Here is some code
    let x = "Wassap";
    console.log(x);
    > Wassap

The grey area is a block of code.

The `//` is how we add comments to our code in JavaScript. Comments are not run with the rest of the code and only act as notes to ourselves and other people that read our code. 

`console.log()` is an in-built JavaScript function that prints the return value of the code to the JavaScript console. A console is an environment/program that can run JavaScript. You can see a console either here on [JS Bin](https://jsbin.com/?js,console) or in the developer tools of your browser.

The `>` sign is used to denote a line showing the return value of a function. 

Got it? Great!

Let's dig in.

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
Comparison operators compare two values and returns a boolean. JavaScript has two types of equals comparisons, equal `==` and strict equal `===` (threequal). Equals checks to see if the values are the same, irrespective of their types while strict equals compares value and type.

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

In JavaScript we can perform arithmetic on numbers just like we would with a calculator. These include:

- Addition `+`
- Subtraction `-`
- Multiplication `*`
- Exponents `**`
- Division `/`

Another important operator that is common in many programming languages is modulus. Modulus gives us the remainder of the divison of two numbers.

    const x = 17;
    const y = 5;
    console.log(x%y);
    > 2

We can also use increment `++` and decrement `--` to increase or decrease a number by 1.

    const x = 3;
    console.log(x++);
    > 4
    

### Logical
The logical operators are logical "OR" `||` , "AND" `&&` and "NOT" `!`. We have seen how NOT works with the comparison operators (`!==`) but AND and OR are new. We often use logical operators to determine all things or at least one thing fulfil a certain requirement. 

The AND operator needs all of the values to be true in order to return true

    console.log(true && false);
    > false
    console.log(true && true);
    > true

The OR operator needs at LEAST ONE value to be true in order to return true.

    console.log(true || false);
    > true
    console.log(false || false);
    > false

Don't worry if these concepts feel a bit abstract at the moment. You will see how this becomes useful when we start to look into Conditionals (if statements).

## Functions
A function in JavaScript is a block of code that performs a particular task. They enclose a set of statements that we can call as many times as we want. Making our code reusable and [modular](https://www.quora.com/What-is-modular-code-How-do-you-write-it). A function is executed when something invokes (calls) it. Once it's been called, it returns some value.

### Named functions
Functions can be named or nameless (anonymous functions). A named function is declared by using the `function` keyword, followed by the function's name. We then define the functions arguments between round brackets, and the logic between a couple of curly brackets.

    function greetUser(name) {
	    return "Hi there " + name + "!";
    }
    greetUser("Stanley");
	> "Hi there Stanley!"

The `return` keyword literally returns some value as a result of running the function. We can say the function above returns (or evaluates to) the string "Hi there Stanley!".

With ES6 we have these fancy new things called arrow functions `=>`. They are a more concise way of declaring a regular function.

    accountBalance = (bal) => {
	    return "Your balance is $" + bal
	}
	accountBalance(756.69);
	> "Your balance is $756.69"
	
### Anonymous functions
An anonymous function does not have a name. We can call an anonymous function where we declare it (called a self executing anonymous function), or store it in a variable and call it somewhere else. Here is an example of a self executing anonymous function.

    (function(col) {
	    return "The colour of the sky is " + col;
	})("blue");

So that's cool, but what's the point of an anonymous function? And why is it wrapped in round brackets? And what's with the argument coming after the function in it's own brackets?

To answer the first question, we generally use anonymous functions at times when we only want to call/run the function once. 

For the second question, wrapping the function in brackets allows us to parse the function as an expression. It provides the function with its own *namespace*, preventing the contents of the function to be accessible from anything outside of it. Namespacing is important because we don't want the contents of the function to collide with other functions or variables outside of the function. 

And that last question is pretty straight forward. The last brackets (parentheses) containing `("blue")` are actually how we call the function. As it's an anonymous function, we have no name to identify it by like we did with `accountBalance()` earlier, instead we have to call it where we wrote it. 

###  Namespace and Scope

In the previous section we touched on the concept of namespace, and as we discovered, its a way of isolating segments code to prevent it from clashes with other segments. This is created through the concept of *scope*. Essentially in JavaScript we have two types of scope. These are global scope and local scope. The best way to demonstrate scope is through example. 

    // Globally scoped variable
    let car = "Toyota";
    // Cannot access variable 'motorbike' from the global scope
    
	function printBike() {
		// Variable locally scoped to the printBike() function
		let motorbike = "Honda";
		// Can access variable 'car' from this local scope
		return;
	}

Scope determines the namespace of a variable, determining whether or not it is visible to other parts of the code. 

As said before, this is a very important feature, especially for large applications as it prevent variables from colliding and causing bugs in our code. 


## Conditionals
Conditionals are also foundational to almost all programming languages. A conditional is essentially a rule that we set that we want the program to follow. The most common conditional 

## Truthy and falsey  
I think this point is a good time to step back from the syntax of JavaScript, and take a look into one of its quirks. If you've been following along in a JavaScript console you might have noticed 


## Type coercion



## Loops

## Math

## Methods
### String
### Array
### Object

## Events

## DOM manipulation