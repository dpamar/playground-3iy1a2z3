# Tail recursive solution

First solution was definitely iterative : we built N! by building all X! values for X = 1..N

Second solution was defintely recursive : we built N! from the result of (N-1)!

But there is a specific kind of recursive way, called **tail-recursive**. In the previous example, there was a stack of all possible values for N. Although it's pointless when we talk about BF, for other languages it means a virtually very very very long stack of integers, that can lead to some memory issue...

The tail-recursive way is a specific recursion where the call to the sub-problem is the only operation done in the recursive process.
* _F(N) = F(N-1) x N_ is definitely not tail-recursive
* _F(N) = N x F(N-1)_ isn't, either : after calling F(N-1) there is still a multiplication

It seems impossible to write a tail-recursive definition of factorial, doesn't it?

Actually, it is indeed impossible to define **this exact function F** in a tail-recursive manner. However, we can define another function F':
* _F'(N,R) = F'(N-1,R*N)_
* F(N) = F'(N,1)

The main advantage of this implementation is that it doesn't add more and more frames to the stack. Instead :
* we have a state (N,R)
* we apply the same method on our state again and again until we reach a given condition
* final state gives us a result

This recursion pattern is often optimized by compilers. It's also a very efficient way to handle recursions in BF
* It doesn't force us to add more and more values on the stack
* It does not need a real "function" or "subroutine" definition: with BF we can easily apply the same method on a given state again and again (as long as a flag is set on our state to indicate whether we should continue or not).

Actually, tail-recursive way can be considered as a recursion implemented with a similar technique than the iterative way: for (state=...;state not final;) state=F(state). But again, the philosophy behind is different : we compute the result based on results for smaller inputs, and not iteratively

# Let's start

* Memory: N 0 0 0 0 0
* Cursor: first cell
* Input: any

# Process

* Set result to 1 (2nd cell)
* _invariant: memory is A, B with A! x B = N!_
* while A is not null
  * decrease A
  * copy "A-1"
  * multiply B by A-1
  * add Bx(A-1) to B to get AxB
* loop
* _A = 0, so B = N!_

# Code
```
>+<                            Set result to 1
[                              while A is not null
  -[->>+>+<<<]>>>[-<<<+>>>]<   decrease and copy A
  [-<[->>+>+<<<]>>[-<<+>>]<]   get AxB
  >>[-<<<+>>>]                   ** part 2 **
<<<<]                          loop
  
```

# Minified version
```
>+<[-[->>+>+<<<]>>>[-<<<+>>>]<[-<[->>+>+<<<]>>[-<<+>>]<]>>[-<<<+>>>]<<<<]
```

# Final state

* Memory: 0 N! 0 0 0 0
* Cursor: first cell
* Input: unchanged
* Output: unchanged

## Test program

This programs prints `x`, code 120 = 5!

```
+++++>+<[-[->>+>+<<<]>>>[-<<<+>>>]<[-<[->>+>+<<<]>>[-<<+>>]<]>>[-<<<+>>>]<<<<]>.
```

