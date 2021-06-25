---
layout: post
title:      "TWO Arrays"
date:       2021-06-25 14:01:12 +0000
permalink:  two_arrays
---


This one threw me for a little bit of a loop.

...that was unintentional.

Anyway

> Given two arrays of integers nums and index. Your task is to create target array under the following rules:

>Initially target array is empty.
>From left to right read nums[i] and index[i], insert at index index[i] the value nums[i] in target array.
>Repeat the previous step until there are no elements to read in nums and index.
>Return the target array.

>it is guaranteed that the insertion operations will be valid.
>


Ok first of all lets start the function and and add an if statement up top saying if the nums array length doesnt equal the index array length that it will return null

```
let createTargetArray = function(nums, index) {
    if(nums.length !== index.length){
        return null
    }
```
		
Now we create the targetArray and set it as an empty array
		
	  let targetArray = []

Ok here we set up our for loop to essentially just count up from 0 that will go for the length of the nums array.

        
    for(let i = 0; i < nums.length; i++){
		
This bit tripped me up because for a good chunk of time I had it in my head that I had to run a loop for each array, but since im essentilly just counting up from 0 for the length of the array I can use i for both arrays. 

So here i used .splice to assign nums to the new array accoridng to the index array.

        targetArray.splice(index[i], 0 ,nums[i])
        
 and here we return the  new array
 
 
```
    }
    return targetArray
};
```

All together now.


```
let createTargetArray = function(nums, index) {
   
	   if(nums.length !== index.length){
        return null
    }
		
    let targetArray = []

     for(let i = 0; i < nums.length; i++){
          targetArray.splice(index[i], 0 ,nums[i])
       }
    return targetArray
};
```

This one was a little tricky for me since I hadn't used a whole lot of .splice (which for the sake of honesty i had typed out as .slice for like 45 minutes and I couldnt understand why it wasnt working. That reason being I was being dumb.) Which highlights the need to really nail down your fundamentals. 

Please go forth and code some more ill see you next week.

