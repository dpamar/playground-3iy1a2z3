# Welcome!

Welcome to this new playground about the BF language. Make sure you already read 
* [Getting started with BrainFuck](https://tech.io/playgrounds/50426/getting-started-with-brainfuck/welcome)
* [BrainFuck part 2 - Working with arrays](https://tech.io/playgrounds/50443/brainfuck-part-2---working-with-arrays/welcome)
* [BrainFuck part 3 - Write a BF interpreter in BF](https://www.codingame.com/playgrounds/50446/brainfuck-part-3---write-a-bf-interpreter-in-bf/welcome)
* [BrainFuck part 4 - Advanced maths](https://www.codingame.com/playgrounds/50446/brainfuck-part-3---write-a-bf-interpreter-in-bf/welcome)
* [BrainFuck part 5 - Math sequences](https://www.codingame.com/playgrounds/50478/brainfuck-part-5---math-sequences/welcome)
* [BrainFuck part 6 - 16-bit integers](https://www.codingame.com/playgrounds/50482/brainfuck-part-6---16-bit-integers/be-smart)
* [BrainFuck part 7 - Quine (+ some non-BF quine theory)](https://www.codingame.com/playgrounds/50485/brainfuck-part-7---quine-some-non-bf-quine-theory/welcome)
* [BrainFuck part 8 - JS/C#/BF Multi quine](https://www.codingame.com/playgrounds/50499/brainfuck-part-8---jscbf-multi-quine/welcome)
* [BrainFuck part 9 - Sort arrays with Bubble and QuickSort](https://www.codingame.com/playgrounds/50516/brainfuck-part-9---sort-arrays-with-bubble-and-quicksort/quicksort)
* [BrainFuck part 10 - RPN calc tool](https://www.codingame.com/playgrounds/50553/brainfuck-part-10---rpn-calc-tool/welcome)

playgrounds if you didn't already !

The goal of this playground is to compare different ways to implement recursion based on a very common example: factorial

It may be hard to understand how we can define a recursion in a language that does not even allow functions. But functions are just one way to implement recurion.

Actually the main difference between recursion and iteration is : in order to solve a given problem
* the iterative way solves the problem, starting from a simple version and getting closer to the solution by incrementing the initial result
* the recursive way solves the problem, defining the solution as a function of solutions to the same problem for smaller instances

It can be proven that both ways are equivalent, and that an algorithm that uses one of these can be re-implemented using the other one.

# Factorial function

The factorial function `!` is recursively defined by
* factorial(0) = 0! = 1
* factorial(n) = n! = n x factorial(n-1)

Let's see different ways to implement this function using BF
