---
layout: post
title:      "Birthday Candles"
date:       2021-07-04 16:07:01 +0000
permalink:  birthday_candles
---


Alrighty, lets do one with some real world stakes.

This one is about Birthday Candles.

> You are in charge of the cake for a child's birthday. You have decided the cake will have one candle for each year of their total age. They will only be able to blow out the tallest of the candles. Count how many candles are tallest.

> Example
> 
> 
> The maximum height candles are 4 units high. There are 2 of them, so return 2 .
> 


Seems straight forward. 

First we'll initialize the function with an imput of an array names candles and the variables that we'll be using

```
function birthdayCakeCandles(candles) {
     let maxHeight = 0
     let count = 0
```

Next we'll just set up our for loop to loop over the length of the array, nothing crazy
		 
        for (let i = 0; i < candles.length; i++ ) {
				
If i is greater than maxHeight, maxHeight will set to the value of i and count will initialize at 1

        if (candles[i] > maxHeight ){
            maxHeight = candles[i]
            count = 1
						
If i equals maxHeight the count will increment by 1
            
        } else if (candles[i] === maxHeight) {
            count += 1
        }
at the end of the loop count is returned
        
    }
return count
}

leaving us with 

```
function birthdayCakeCandles(candles) {
     let maxHeight = 0
     let count = 0
        for (let i = 0; i < candles.length; i++ ) {
        if (candles[i] > maxHeight ){
            maxHeight = candles[i]
            count = 1
            
        } else if (candles[i] === maxHeight) {
            count += 1
        }

        
    }
return count
}
```

Not too complicated. I got jammed up by having too few variables at first and counting the wrong thing so the return was always spitting out the count of the array.

It was a good reminder for me to always name your variables appropriately, they dont always need to be x and y.

Later gamers.


