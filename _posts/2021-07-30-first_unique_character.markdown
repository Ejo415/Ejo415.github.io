---
layout: post
title:      "First unique character"
date:       2021-07-30 20:53:40 +0000
permalink:  first_unique_character
---


Alright, you know whats up. Leetcode. 

Lets jump right in this week as im presently too exhausted to be overly clever. Sincerest apologies.

> Given a string s, find the first non-repeating character in it and return its index. If it does not exist, return -1.
> 

Pretty straight forward. So lets jump in. (feel free to give it a shot then come back)

create the fucntion yadda yadda, and then we'll kick off two variables. `frequencies` which will be an empty object to hold our map of s and` result`, which will be our fallback return of -1

```
var firstUniqChar = function(s) {
    let  frequencies = {};
    let result = -1
```

Next we set up our first loop (thats right i said first) where we will either add the character and set its value to 1 or increment the value if the character is already in the `frequencies` object
    
    for (let char of s){
        if (frequencies[char] === undefined){
            frequencies[char] = 1;
            
        }else{
            frequencies[char]++;
        }
    }
		
Now for the second loop again but for this we'll set up a variable called `char` which will just be the character at whatever i is on this loop (this will make our lives WAY easier) 

We then check this loop against the `frequencies` object and return the index of the first character that has a value of 1 in `frequencies`
    
    for (let i = 0; i < s.length; i++){
        let char = s.charAt(i);
        
        if (frequencies[char] === 1){
            return i
        }
    }
		
And after all of that if there are no unique characters in s we will return out value of -1
    
 ```
return result
};
```

Put it all together and...
```

var firstUniqChar = function(s) {
    let  frequencies = {};
    let result = -1
    
    for (let char of s){
        if (frequencies[char] === undefined){
            frequencies[char] = 1;
            
        }else{
            frequencies[char]++;
        }
    }
    
    for (let i = 0; i < s.length; i++){
        let char = s.charAt(i);
        
        if (frequencies[char] === 1){
            return i
        }
    }
    
    return result
};
```

Now go do better than I did. According to leetcode you have a 52.19% chance of doing so.

Till next time
