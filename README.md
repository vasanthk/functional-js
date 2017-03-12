# Functional Programming in JavaScript

### What is Functional Programming?

In computer science, functional programming is a programming paradigm that treats computation as the evaluation of mathematical functions and avoids state and mutable data. It emphasizes the application of functions, in contrast to the imperative programming style, which emphasizes changes in state. Functional programming has its roots in lambda calculus, a formal system developed in the 1930s to investigate function definition, function application, and recursion. Many functional programming languages can be viewed as elaborations on the lambda calculus.

It is the process of building software by composing pure functions, avoiding shared state, mutable data, and side-effects.
Functional programming is declarative rather than imperative, and application state flows through pure functions.
Contrast with object oriented programming, where application state is usually shared and colocated with methods in objects.

### Purity

In functional programming, we strive to use “pure” functions as much as possible. When a function isn’t pure, it has the potential to act unpredictably.

There are two qualities that make a function “pure”:

* The function depends only on the input provided to it to produce a result (and not on any external state).

* The function does not cause any observable side effects, such as modifying a global object or modifying a parameter passed by reference.

**Benefit 1**: Pure functions are predictable

**Benefit 2**: Pure functions are easy to test

There are plenty of other reasons to use pure functions in functional programming. Beyond being easier to refactor and debut, pure functions are also deterministic and well-suited for parallel processing.

Our ultimate goal here as functional programmers is not to eliminate side effects, but confine them. We strive to minimize the amount of impure code, and segregate it from the rest of our program.

### Immutability

When data is immutable, it’s state cannot change after it’s created. If you want to change an immutable object, you don’t. Instead, you create a new object with the changed value and point your reference to it.

Why does functional programming use immutable data in the first place?

In short, immutable data is important because we need to be able to attach dependable, unchanging values to our functions. Something crazy happens when you treat all data as fixed values: the concept of time goes away.

Goodbye to side-effects that can change an expression’s value. Goodbye to worrying about whether some piece of data is the same as what you expected it to be. When you have this guarantee, functions can now be evaluated at any time and in any order and the result is guaranteed to always be the same.

Overall, there are many other benefits to immutability in functional programming. They make values easy to share, they make it safer and easier to do concurrent programming, they avoid temporal coupling, they eliminate defensive copies, and much more.

### Referential Transparency

If a function consistently yields the same result for the same input, it is referentially transparent. It gives us the ability to freely replace an expression with its value and not change the behavior of the program.

Here’s a more general way to think about referential transparency:

**Pure functions + immutable data = referential transparency**

**Benefit 1**: Makes it much easier to refactor and rewrite programs. Since a pure, referentially transparent function can be freely replaced by it’s value, the only thing we have to worry about when we refactor it is that we get the same value for a given input.

**Benefit 2**: Particularly helpful for optimizing code using memoization, common subexpression elimination, lazy evaluation, or parallelization.

### Functions as first-class citizens

The ability to treats functions as values let’s us use is as a first-class function. We can:

* Refer to it from constants and variables

* Pass it as a parameter to other functions

* Return it as result from other functions

Well, if we’re allowed to throw functions around like data, then we can also start to combine functions with other functions to create new functions and new behavior. This leads to all sorts of “functional” processes like composition, partial application, currying, and etc.

The big takeaway here: always remember that functions are treated just like data in functional programming. We can refer to them from constants and variables, pass them as parameters to other functions, and return them as results from other functions. That’s what makes them “first-class citizens.”

## Reference

[What is Functional Programming?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-functional-programming-7f218c68b3a0#.ip0v7pbkq)

[Why Learn Functional Programming in JavaScript? (Composing Software)](https://medium.com/javascript-scene/why-learn-functional-programming-in-javascript-composing-software-ea13afc7a257#.haphei83h)

[Learn the fundamentals of functional programming](https://medium.freecodecamp.com/learning-the-fundamentals-of-functional-programming-425c9fd901c6#.8zk87ycto)

[Why Learn Functional Programming in JavaScript? (Composing Software)](https://medium.freecodecamp.com/functional-programming-in-js-with-practical-examples-part-1-87c2b0dbc276)

[Get Functional](https://blog.daftcode.pl/get-functional-3eaceb76258f)

[A Functional Programmer’s Introduction to JavaScript](https://medium.com/javascript-scene/a-functional-programmers-introduction-to-javascript-composing-software-d670d14ede30#.ba08vt5af)

[The Rise and Fall and Rise of Functional Programming (Composing Software)](https://medium.com/javascript-scene/the-rise-and-fall-and-rise-of-functional-programming-composable-software-c2d91b424c8c#.wo5ff5ura)

[Is Javascript a Functional Programming Language?](http://softwareengineering.stackexchange.com/questions/127672/is-javascript-a-functional-programming-language)

## Videos

[Functional Programming in JavaScript](https://www.youtube.com/watch?v=BMUiFMZr7vk&list=PL0zVEGEvSaeEd9hlmCXrk5yUyqUag-n84)

[If you know map, I will teach you monads - Mattias Petter Johansson](https://www.youtube.com/watch?v=2jp8N6Ha7tY)

[Learning Functional Programming with JavaScript - Anjana Vakil](https://www.youtube.com/watch?v=e-5obm1G_FY)