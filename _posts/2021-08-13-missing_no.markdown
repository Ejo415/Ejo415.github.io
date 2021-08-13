---
layout: post
title:      "Missing No"
date:       2021-08-13 20:33:04 +0000
permalink:  missing_no
---


Im not gonna lie its gratifying to be able to work a Pokemon reference into the title like that.

Anyway on to our Leetcode for the week, this one is called Missing Number and im told is (or was) a question that Amazon has used before in interviews.

> Given an array nums containing n distinct numbers in the range [0, n], return the only number in the range that is missing from the array.
> 
> Follow up: Could you implement a solution using only O(1) extra space complexity and O(n) runtime complexity?
> 
 
 Ignore the second part, this solution will meet that anyway.
 
 SO
 
 First we yadda yadda the new function and the variables.
 
 sumIfNoneMissing is being initialized with nums.length. This variable as the name might suggest is going to be the sum of the array if there *wasnt* a number missing. So what we'll be doing with this is adding the indicies of the array was we loop through it + the length of the array.
 
 actualSum is starting at 0 and will just be the real sum of the array.
 
 
```
var missingNumber = function(nums) {
    let sumIfNoneMissing = nums.length
    let actualSum = 0
```

Now, our standard for loop with the indicies being added to sumIfNoneMissing and each number of the nums array being added to actualSum 

    for (let i = 0; i < nums.length; i++){
        sumIfNoneMissing += i;
        actualSum += nums[i]
				
Now for the end we subtract those two numbers and that will be the missing number from the array.

```
    }
    return sumIfNoneMissing - actualSum
};
```


all together now

```
var missingNumber = function(nums) {
    let sumIfNoneMissing = nums.length
    let actualSum = 0
    
    for (let i = 0; i < nums.length; i++){
        sumIfNoneMissing += i;
        actualSum += nums[i]
    }
    return sumIfNoneMissing - actualSum
};
```

nothing too crazy, this is more of a head scratcher logic wise at first but the actual code in the end was pretty straight forward. 

Let this be another lesson on "why not to over think everything"

also my solution is faster than 73.85%

Go do better.

See you space cowboy.


