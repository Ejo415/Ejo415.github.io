---
layout: post
title:      "Meet at the Intersection"
date:       2021-08-09 01:35:32 +0000
permalink:  meet_at_the_intersection
---


MORE ARRAYS

Fun I know.

Anyway this week on leetcode were doing a problem called Intersection of Two Arrays.

> Given two integer arrays nums1 and nums2, return an array of their intersection. Each element in the result must be unique and you may return the result in any order.
> 

Ok so first thing we're going to do is declare a variable called firstSet which is a new Set (we're using set because each set can only contain unique values so we cannot have doubles)

```
var intersection = function(nums1, nums2) {
    let firstSet = new Set();
```

Next we'll kick off our first loop to just add each unique value in the first array nums1 into the first set.
    
    for (let num of nums1){
        firstSet.add(num)
    }
		
Now we initialize a new variable called commonSet which is where we will have our final return values.
    
    let commonSet = new Set();
		
Now we set off our second loop where we will loop through nums2 and if the value is contained in firstSet we will add it to commonSet.
    
    for (let num of nums2){
        if (firstSet.has(num)){
            commonSet.add(num)
        }
    }
		
and finally we will return the commonSet using Array.from to covert it to an array

```
  return Array.from(commonSet)
};
```

Altogether we've got

```
var intersection = function(nums1, nums2) {
    let firstSet = new Set();
    
    for (let num of nums1){
        firstSet.add(num)
    }
    
    let commonSet = new Set();
    
    for (let num of nums2){
        if (firstSet.has(num)){
            commonSet.add(num)
        }
    }
    return Array.from(commonSet)
};
```

I personally need to start getting used to using Sets more which this problem highlighted a bit for me.

I only did better than 30% so please go forth and beat me.

Till next time.


