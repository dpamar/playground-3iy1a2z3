# The iterative way

Factorial can be computed using an iterative way : let result be 1, then for each value V between 1 and N, multiply result by V.

# Let's start

* Memory: N 0 0 0 0 0 
* Cursor: first cell
* Input: any

# Process

* set result to 1 
* set current index to 0
* _invariant: result = (current index)! and first cell + current index = N_
* while first cell is not null
  * increase index
  * multiply result by current index
  * decrease first cell
* loop
* _first cell = 0, so current index = N and result = N!_

# Code
```
>>>>+                        set result to 1 (and current index to 0)
<<<<[                        while first cell is not null
  >[->+>+<<]>[-<+>]>         copy current index
  [->[->+>+<<]>[-<+>]<<]     multiply result by current index
  >>>[-<<+>>]<<<<<+          increase current index and store result x new index into result
<-]                          decrease first cell and loop
```

# Minified version
```
>>>>+<<<<[[->+>+<<]>>[-<<+>>]<-[->>>[-<+<+>>]<[->+<]<<]>[->>+<<]<<-]
```

# Final state

* Memory: 0 N 0 0 N!
* Cursor: first cell
* Input: unchanged
* Output: unchanged

# Test program

This programs prints `x`, code 120 = 5!

```
+++++>>>>+<<<<[>[->+>+<<]>[-<+>]>[->[->+>+<<]>[-<+>]<<]>>>[-<<+>>]<<<<<+<-]>>>>.
```
