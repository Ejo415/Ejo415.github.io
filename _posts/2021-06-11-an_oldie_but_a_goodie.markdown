---
layout: post
title:      "An oldie but a goodie."
date:       2021-06-11 19:28:29 +0000
permalink:  an_oldie_but_a_goodie
---


FizzBuzz

You may have heard of it as its a pretty well known algo problem. So lets get into it.

> Given the integer **n** return a string array containing every number counting up to **n** however if the number is divisible by 3 return 'Fizz', if the number is divisible by 5 return 'Buzz" and if the number is divisible by both reutrn 'FizzBuzz'
> 


So lets get going, shall we?

First we initialize the function and the result array

```
let fizzBuzz = function(n) {
    let result = []
```

next we fire up our old friend the for loop and a variable set to an empty string within the loop.
		
  ```
  for (i = 1; i <= n; i++){
       let str = ''
```

Now for our first if statement. so if i is divisible by 3 set the string (on this loop) to 'Fizz'
			 
			 
	if (i % 3 === 0){
			str += 'Fizz'
	}
	
if divisible by 5, set to buzz. (now if its divisible by both it will return FizzBuzz) 
				
				
        if (i % 5 === 0){
            str += 'Buzz'
        }
				
here if the string is empty (which it will be since its a new loop) the string set itself to whatever i is on this loop

        if (str.length === 0){
            str += i
        }
				
and here is where after each loop the string variable gets pushed into the result array and then returns the array


     result.push(str)   
    }
        return result   
				};
				
				
Here is the whole shebang

```
let fizzBuzz = function(n) {
    let result = []
    for (i = 1; i <= n; i++){
       let str = ''
        if (i % 3 === 0){
            str += 'Fizz'
        }
        if (i % 5 === 0){
            str += 'Buzz'
        }
        if (str.length === 0){
            str += i
        }
     result.push(str)   
    }
        return result   
};
```
Not as scary as it sounds going into it. There are different ways to do it, such as doing away with the string variable entirely and pushing the loop results directly into the result array but that takes a smidge bit of refactor. Theres a more efficient way to do this but ill let you play around with it on your own to figure out.

Till next time.

