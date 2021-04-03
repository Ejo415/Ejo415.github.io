---
layout: post
title:      "Big O....ohhhh boy"
date:       2021-04-03 17:44:15 +0000
permalink:  big_o_ohhhh_boy
---


Ok before I start I want you to take a deep breath, maybe go grab a drink or something. 

Done?

Cool.

Ok now ill try and keep this as simple as I can. So a while ago I touched on time complexity a bit and only mentioned Big O. NOW ive gotten around to diving back into it again so here are the basics.

Big O Notation is how we as programmers measure the performance of specific algorithims, here i'm going to be going over a few examples of algorithims and how they're measured. 

First im going to show you 2 different algorithims that do the exact same thing. the function is going to add all numbers counting up to n. For example if n = 6 then what the function will do is 1+2+3+4+5+6.


```
A.   1      function addToN(n) {
       2       let total = 0
			 3        for (let i = 1; i <= n; i++) {
			 4       total += i
			 5        }
			 6	    return total
			 7	  }
```

Here is a basic loop, and in the loop we've got 5 operations. Three on the line 3, and the += on line 4 counts as two since it will add to the total and then produce a new total and on top of THAT there is the return and the initial declaration of total = 0 so it comes out to be 5n+2. 

The hitch of course is that since this is a loop that 5 multiplies by n so the actual number of operations scales depending on the value of n. which if n get high enough will drag everything down pretty hard. So the notation of this would be O(5n+2) but to simplify it even more we can just call this O(n) since regardless of the other numbers the functions will always scale to n.

Now lets look at a function that does the same thing but written differently .

```
B.  1         function addToN(n) {
      2           return n * (n+1) / 2;
		3        }
```

Gotta love one liners. This does the same thing as the first one but more math-y. In THIS function there isnt a loop so the amount of operations isnt dependant on n so here we will ALWAYS just have 3 operations(the * the + and the /) resulting in a consistantly fast algorithim. This one is going to come out to O(3) simplified to O(1) since it will always be a constant number of operations.

There is one more type I want to quickly go over and thats O(n^2) this is something we get when we have a nested loop.

```
function printPairs(n) {
  for (let i = 0; i < n; i++) {
    for (let j = 0; i < n; j++) {
  console.log(i, j)
    }
  }
}
```

As you can see *two* loops are run for n so the number of operations is exponentially increased. This particular one is simplified to O(n^2)

To recap

O(n) - while it is dependant on what n will be will always have a predictible and linear rise in time complexity.
O(1) - will always be consistant as the number of operations does not depend on n
O(n^2) - is similar to O(n) except instead of being dependant on n its dependant on the square of n. this is quadtratic time complexity.  

Ok im down now. Go drink some water ot eat a hot pocket or something.

Ill be back with more of this nonsense next week.
