# ES6 (ES2015) Cheat Sheet

## `let` and `const`

`let` and `const` are new ways of declaring variables instead of using `var`.  For example:

```
let x = 20;
const y = 30;
```

The first major difference is that `var` is **function scoped** whereas `let` and `const` are **block scoped**.  Basically whereever you have curly brackets `{}` you have block scope.

An example of this is using a `for...loop`:

```
for (var i = 0; i < 5; i++) {
    console.log(i)
};

// Output
0
1
2
3
4

console.log('i = ' + i);

// Output
i = 5
```

Even outside the loop, `i` is accessible, it's now in the *global scope*.

Now with `let`:

```
for (let x = 0; x < 5; x++) {
    console.log(x)
};

// Output
0
1
2
3
4

console.log('i = ' + i);

// Output
ReferenceError: x is not defined
```

As `x` is **block scoped** it's not accessible outside the loop.

An important aspect to remember, is that whilst `var` is [hoisted](https://scotch.io/tutorials/understanding-hoisting-in-javascript#toc-hoisting-variables) to the top of its enclosing scope, `let` and `const` are not.

The difference between `let` and `const` is that you can redeclare a value for `let`, but not for `const`.

```
let a = 3;
const b = 5;

a = 6; // No issues
b = 10 
// Output
TypeError: Assignment to constant variable.
```

If you know that do not want a variable to be reassigned then use `const`, otherwise use `let`.



## Template Strings

Template strings are a new way to work with strings.  The syntax is easy, simply wrap your string with backticks instead of quotes

```
let myString = `Hello world`;
```
The advantage is using template strings is mainly in the ability to span several lines and to interpolate variables and expressions.

**Multiline example**
```
const myString = `Hello 
World`;

console.log(myString)

// Output
Hello World

const myOtherString = "Hello 
World";

// Output
Uncaught SyntaxError: Invalid or unexpected token
```

**Interpolation example**

Interpolation is done using the syntax `${....}`

```
const name = 'Bob';
const myString = `Hi ${name}, how are you?`;

console.log(myString);

// Output
Hi Bob, how are you?
```

You can even use logic inside your string template

```
const a = 2, b = 3;

console.log(`a plus b = ${a + b}`);

// Output
a plus b = 5
```

### Arrow functions

Arrow functions are a new way of declaring [function literals](https://stackoverflow.com/questions/12314905/exact-meaning-of-function-literal-in-javascript).

```
const myFunction1 = x => {
    return x * 2;
}
```

Ifthe function body fits on one line, you can omit the curly brackets 

```
const myFunction1 = x => x * 2;
```

It's important to note that if your function is inside a block `{....}` then you must use a `return` statement.

With 2 or more arguments, brackets are needed around the arguments

```
const myFunction2 = (a, b) => {
    return a + b;
}
```

If no arguments are needed

```
const myFunction3 = () => {
    ....
}
```

A common use of arrow functions is inside methods such as `map`

```
const myArr = [1, 2, 3];

myArr.map(element => {
    return element * 2;
});

// Output
[2, 4, 6]

// Or even more concise
myArr.map(element => element * 2);

// Output
[2, 4, 6]
```

The biggest difference to remember when using arrow function is that the keyword `this` becomes *lexically bound*, meaning that it uses `this` from the code that contains the arrow function.  In the pre-ES6 syntax `this` would have been based on the context of where the function was called.

```
const myButton = document.getElementById('btn');
myButton.addEventListener('click', () => {
  this.classList.toggle('on');
});
```

Would return a *Typeerror* as `this` would not be bound to the button, but instead it would be bound to the parent scope of the function.