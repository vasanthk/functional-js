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

### Higher Order Functions

Higher-order functions are functions that work on other functions, meaning that they can take one or more functions as an argument and can also return a function as a result.

One of the key reasons for using higher-order functions is that they allow us to define computations by defining what we want instead of how to get it explicitly. This makes it much easier to understand the program as a whole, because we don't have to look at the for-loop and figure out what's going on.
A great use case for higher-order functions is to replace loops with collection-iteration functions, such as reduce, map, and filter.

### Composition

Once you get used to passing functions around like data, you’ll quickly start to discover ways to combine two or more functions together. This is known as function composition.
To perform function composition, you simply have the result of each function be passed as the argument to the next, and treat the result of the last function in the sequence as the result of the whole.

Essentially, composition allows us take small, reusable, and independent functions and compose them together in various ways to build up much bigger programs. Rather than thinking about new functionality as adding and extending new methods to classes like we would in object-oriented programming, we simply create new functions and use composition to neatly knit them together.

### Partial Application

Partial application is a way to turn a function that expects multiple parameters into one that will keep returning a new function until it receives all its arguments. In other words, if a function accepts multiple parameters, we can “partially apply” some of the arguments now, filling in the rest later.
We do this by creating intermediate functions that have just the arguments we provided applied to them (while waiting for the rest of the arguments to be supplied).

**What’s the point of partial application?**

In short, partial application allows us to partially apply certain argument to create new functions out of existing ones. The ability to take a generic function and specialize it by passing in certain arguments is incredibly useful.

### Currying

Currying is the process of taking a function that accepts N arguments and turning it into a chained series of N functions that each take one argument.

It sounds a lot like partial application, doesn't it? It takes a function and an argument, and returns a new function with the argument applied to it. So what’s the difference? The difference is that with currying, you can never provide more than one argument — it has to be either one or zero.

Remember that with partial application, we can apply more than one argument at a time. If a function takes 5 arguments, we can partially apply 3 of them. But with currying, we only pass one argument at a time. So if a function takes 5 arguments, we have to curry 5 times before we get the resulting value.

### Declarative Programming Paradigm

Functional programs are “declarative”. A declarative program declares “what” the program does without necessarily telling us “how” it does it.

First, : FPFunctional programming strives for expressive and easy to understand code. The declarative example above wins on both counts, being both expressive, short, and easy to understand at a glance.

Secondly, functional programming strives to use small, independent, reusable, and composable functions as the primary unit of abstraction. Loops (such as those in the imperative example above) aren’t reusable artifacts.

Lastly, declarative code typically leads to less code—and that means fewer places for bugs to hide.

Long story short:

**Declarative = WHAT**

**Imperative = HOW**

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