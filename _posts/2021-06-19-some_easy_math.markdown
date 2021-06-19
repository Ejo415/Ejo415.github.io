---
layout: post
title:      "Some Easy Math"
date:       2021-06-19 17:12:45 +0000
permalink:  some_easy_math
---


Continuing through leetcode, we have the following:

> Given an integer number n, return the difference between the product of its digits and the sum of its digits.
> 

So given what we've done in the past few weeks the solution shouldn't be too far of a leap.

First we initialize the function and variables for product (with it set to 1 because multiplying anything against a starting value of 0 is...stupid), sum and a variable that takes in the digits of the integer and makes it into a string to it can be interated though.

```
let subtractProductAndSum = function(n) {
    let nStr = n.toString()
    let p = 1
    let s = 0
```
	
Next is our best friend the for loop
		
` for(let i = 0; i < nStr.length; i++){`

Now that we're iterating through every digit in the number we can add or mulitply each digit against the sum and product variables (with the digits getting run through parseFloat() because when I did without the numbers were just getting added as a string like "0", "02", "021" etc)

       s += parseFloat(nStr[i])
       p *=nStr[i]
    }
		
Finally just return the product minus the sum

```
  return p - s
};
```
All together we've got

```
let subtractProductAndSum = function(n) {
    let nStr = n.toString()
    let p = 1
    let s = 0
for(let i = 0; i < nStr.length; i++){
       s += parseFloat(nStr[i])
       p *=nStr[i]
    }
    return p - s
};
```

Nothing too hard, soon ill start moving more outside more easy problems. Maybe even *gasp* a medium.

Till next week gamers.


