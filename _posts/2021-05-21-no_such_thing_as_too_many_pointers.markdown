---
layout: post
title:      "No such thing as too many pointers"
date:       2021-05-21 20:18:56 +0000
permalink:  no_such_thing_as_too_many_pointers
---


So continuing last weeks post, we have another problem. This one will utilize multiple pointers to solve.

```
Implement a function called countUniqueValues which accepts a sorted Array, and counts the unique values in the Array. There can be negative numbers in the Array, but it will always be sorted.
```

ok SO.

```

function countUniqueValues() {
//first initialize your two pointers that will go through the array
//iterate through array with one pointer while it compares itself to second pointer
//note when values change
//return number of unique values
}
```

Lets do this thing. First the obligatory edgecase to return 0 if the array is empty

```
function countUniqueValues(arr) {
if (arr.length === 0) return 0;
```

Next, initialize your pointers.starting one at index 0 and one at index 1

```
let left = 0;
let right = 1;
```

Now we're gonna start a while loop that will run until the index that started at 1 reaches the end of the array and so long as the two pointers match it will continue to move down it.

```
while (right < arr.length) {
     if (arr[left] === arr[right]) {
       right++;
     } else
		 
```

If the numbers DONT match the left pointer will increment and then equal its value to what the right pointer is. The right pointer will now increment.

```
else {
       left++;
       arr[left] = arr[right];
       right++;

```

Then, just return the left pointer +1 to account for 0 

```

        }
      }
   return left + 1;
 }

```

All together we've got this.

```

function countUniqueValues(arr) {
   if (arr.length === 0) return 0;
   let left = 0;
   let right = 1;
   while (right < arr.length) {
     if (arr[left] === arr[right]) {       
		 right++;
     } else {
       left++;
       arr[left] = arr[right];
       right++;
     }
   }
   return left + 1;
 }

```

As I said last week, this was the solution *I* used. I know there are better.

Till next time.


