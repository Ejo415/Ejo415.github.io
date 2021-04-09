---
layout: post
title:      "Space Complexity"
date:       2021-04-09 21:02:51 +0000
permalink:  space_complexity
---


Alright kids this might be a bit of a shorter one.

Ive talked about Time Complexity and Big O but theres one more bit thats important to atleast have a basic grasp of (basic grasps being something i excel at) and thats Space Complexity.

Space Complexity is the amount memory an algorithim will need to execute. Some basic rules of thumb are as follows.

1. Most simple data types (booleans, numbers, undefined, null etc. etc.) require a constant space.
2. Strings require O(n) space since n = string length
3. Reference types are also generally O(n) where n would equal the length (for arrays) or the number of keys (for objects).


Some Examples

```
function addArr(arr) {
     let total = 0
    for (let i = 0; i < arr.length; i++) {
     total += arr(i)
     }
   return total
]
```

Overall in this funtion there are onnly two assignments (on lines 2 and 3) and they do not change due to n. So here the space complexty of this is O(1) as its constant.

```
function doubleArr(arr) {
      let newArr = [];
	 for (let i = 0; i < arr.length; i++) {
	   newArr.push(2 * arr[i]);
    	 }
	 return newArr
}
```

here we have a new array (on line 2) thats being manipulated and added too based on n (line 4) so the space complexity will be O(n)

Like I said, short. But it will be important down the line when getting into more complex algorithms and to have a better understanding of Big O as a whole.

Till next time.
