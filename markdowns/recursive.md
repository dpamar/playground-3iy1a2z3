# A first recursive way

Now, let's try to implement a recursion. The recursive call will be
```
factorial(N): return factorial(N-1) x N
```

# Let's start

* Memory: 0 N 0 0 0 0
* Cursor: second cell
* Input: any

# Process

* while N is not null
  * copy N-1 on the right
  * go to the copy
* loop
* write 1 (result for N=0)
* go to previous N value
* while there is a N value
  * multiply N by result
* loop


_Note_: this looks like
* Generate in memory values N, N-1, N-2, ..., 3, 2, 1, 0
* unwind by multiplying values to current result

# Code
```
[                         while current N is not null
  [->+>+<<]>>[-<<+>>]<-   copy N and subtract 1
]                         and loop on this new value
+                         generate result
<[                        while current N is not null
  -[>[->+>+<<]>[-<+>]<<-] multiply result by N minus 1
  >>>[-<<+>>]<<[-<+>]     and add result one more to get result x N
<<]                       loop on next N
```

# Minified version
```
[[->+>+<<]>>[-<<+>>]<-]+<[-[>[->+>+<<]>[-<+>]<<-]>>>[-<<+>>]<<[-<+>]<<]
```

# Final state

* Memory: 0 N!
* Cursor: first cell
* Input: unchanged
* Output: unchanged

# Test program

This programs prints `x`, code 120 = 5!

```
>+++++[[->+>+<<]>>[-<<+>>]<-]+<[-[>[->+>+<<]>[-<+>]<<-]>>>[-<<+>>]<<[-<+>]<<]>.
```
