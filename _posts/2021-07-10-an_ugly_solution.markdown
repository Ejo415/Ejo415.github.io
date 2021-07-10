---
layout: post
title:      "An ugly solution"
date:       2021-07-10 19:31:01 +0000
permalink:  an_ugly_solution
---


So, something ive learned is that sometimes the way to get your code to work is to do something ugly. Now granted, there is probably...most definitely a way to solve this problem is a less ugly way but I havent really tried to go back yet. So lets take the lesson at face value shall we?

> Given five positive integers, find the minimum and maximum values that can be calculated by summing exactly four of the five integers. Then print the respective minimum and maximum values as a single line of two space-separated long integers.
> 
> Example
> 
> `arr = [1,3,5,7,9]`
> 
> The minimum sum is 1 + 3 + 5 + 7 = 16  and the maximum sum is 3 + 5 + 7 + 9 = 24 . The function prints `16 24`
> 

Alrighty, so first we as always, start the function and set an empty variable to work with 

```
function miniMaxSum(arr) {
    let sums = []
```
  
Then we'll add the first 4 numbers in the array and push it to the `sums` array

    sums.push(arr[0]+arr[1]+arr[2]+arr[3])
		
Then, and heres the ugly part, we do that 4 more times sliding down the array.

    sums.push(arr[1]+arr[2]+arr[3]+arr[4])
    sums.push(arr[2]+arr[3]+arr[4]+arr[0])
    sums.push(arr[3]+arr[4]+arr[0]+arr[1])
    sums.push(arr[4]+arr[0]+arr[1]+arr[2])
		
After than awful looking chunk of code we make 2 variables to pull out the largest and smallest value from the sums array


    let min = Math.min(...sums)
    let max = Math.max(...sums)
		
THEN, and heres the part that threw me for a minute. We console log `min` and `max`. I was so used to problems asking for a return It took longer than im willing to admit to notice that a console.log was what I needed.    
   
    console.log(min, max
	}
	
	
All together we have this monster.


```
function miniMaxSum(arr) {
	let sums = []

	// init var arry to hold sums
	sums.push(arr[0]+arr[1]+arr[2]+arr[3])
	sums.push(arr[1]+arr[2]+arr[3]+arr[4])
	sums.push(arr[2]+arr[3]+arr[4]+arr[0])
	sums.push(arr[3]+arr[4]+arr[0]+arr[1])
	sums.push(arr[4]+arr[0]+arr[1]+arr[2])
	//iterate over array to add indexes
	// store sums in sums ar
	//return min and max
	let min = Math.min(...sums)
	let max = Math.max(...sums)


	console.log(min, max)
}
```

Now, in hindsight using the sliding window technique probably would have given a better solution however at the time I didnt think of it. Sometimes you just need to get the function to work to be able to move on and you can always go back to refactor later...which I'll probably do later.



