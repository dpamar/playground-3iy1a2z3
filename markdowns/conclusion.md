# Conclusion

The iterative way is quite easy to implement using BF.

The recursive way can be used as well, even the tail-recursive one.

However, the tail-recursive way is probably better than the non-tail one. Indeed, without function calls in our language, the recursion is based on while...loop structures
* the tail-recursive way looks like a loop. Actually, many compilers optimize tail-recursive codes into loops
* the non-tail-recursive way is also possible but forces the code to get executed over a virtually large portion of our memory

Again, tail-recursive **is not** iterative way: solution is built using solutions for smaller problems, and not from a small problem getting bigger and bigger.

