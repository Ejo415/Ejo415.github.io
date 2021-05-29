---
layout: post
title:      "Almost but not quite."
date:       2021-05-29 18:17:17 +0000
permalink:  almost_but_not_quite
---


Ok, question number 3 in our {?} part series of me breaking down some assorted algo problems.

```
Write a function called sameFreqency. Given two positive integers find out of the numbers have the same frequency of digits. Must be O(n)
```

Judging by the question alone you can tell this is going to be a similar solution to the first question we did with anagrams, so lets do this thing shall we?

The first thing we're gonna want to do is convert both of the input integers to strings so we can iterate through them more easily. (It took me longer than id care to admit to remember to do this)


```
function sameFrequency(int1, int2) {
  let strInt1 = int1.toString();
  let strInt2 = int2.toString();
```
	
	
Next we initialize two empty objects to keep what we track stored.
	
	
	
```
let num1 = {};
let num2 = {};
```
	
	
	
After that we initialize two for/of loops to iterate through the respective numbers and count the individual values so we can compare them in a second. (Much how we looped through the strings for the anagrams.
	
	
	
 ```
for (let number of strInt1) {
	num1[number] = (num1[number] || 0) + 1;
}
for (let number of strInt2) {
	num2[number] = (num2[number] || 0) + 1;
}
```

	
	
finally we loop through the keys in `strInt1` and compare them to the keys in `strInt2`, if they match we return true if they dont we return false.
	
	
	
```
for (let key in num1) {
	if (num1[key] !== num2[key]) {
		return false;
	}
}
return true;
}
```

All together we have this.


```
function sameFrequency(int1, int2) {
  let strInt1 = int1.toString();
  let strInt2 = int2.toString();
  let num1 = {};
  let num2 = {};
  for (let number of strInt1) {
    num1[number] = (num1[number] || 0) + 1;
  }
  for (let number of strInt2) {
    num2[number] = (num2[number] || 0) + 1;
  }

  for (let key in num1) {
    if (num1[key] !== num2[key]) {
      return false;
    }
  }
  return true;
}
```

Frankly i probably should have put an if statement at the top to cover some edgecases but i didn't realize that until after the tests had passed. Other than *THAT* like I said its similar to the anagram problem from earlier but converting the integers to strings is an impotant distinction that I thought was good to shine a light on. 

How would you solve it?

	
	
	
	

