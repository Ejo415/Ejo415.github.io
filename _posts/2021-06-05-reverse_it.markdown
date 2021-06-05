---
layout: post
title:      "Reverse it"
date:       2021-06-05 19:00:24 +0000
permalink:  reverse_it
---


Hey kids, back at it with the problems this week. I actually did this one yesteday so its still a bit fresh in my mind. 

> Given an interger x, return x with the digits reversed.

So already we're starting off a bit different. I made this function into an arrow function because in the end it turned out to be a little bit faster on the execution. It doesnt ALWAYS make you functions faster but it never hurts to check. it made mine faster by about 20-30 ms.

Function type aside I made the variable into a string so I could iterate through it and I made and empty array to hold everying in.

```
let reverse = (x) => {
    let num = x.toString()
    let newNum = []
```

Here is the standard-ish for loop. I set i for the END of the string that i just created from x and ran it backwards to index 0 of the string. 

	for(let i = num.length -1; i >= 0; i--){
	
			 
This looks to see if the original x was a negative number by looking for a "-" in num, if it sees the "-" it unshifts it to the front of the array.
			 
	 if( num[i] === "-"){
		newNum.unshift("-")
	 } else {
		newNum.push(num[i]) 
	 }

}
    
Finally we take the array of string and combine them into one number with .join('') and then run that through parseFloat to get the final number to return as the result (parse float will also remove any 0 at the front of the number IE it will return 21 as opposed to 0021)
		
```
   let result = newNum.join('')
   parseFloat(result)
	 
   }
    return result
};
```

Altogether we have

```
 let reverse = (x) => {
	let num = x.toString()
	let newNum = []
	for(let i = num.length -1; i >= 0; i--){
		 if( num[i] === "-"){
			newNum.unshift("-")
		 } else {
			newNum.push(num[i]) 
		 }
}
 let result = newNum.join('')
 parseFloat(result)
 }
	return result
};
```
Ok now Im gonna need you all, when you inevitable do this problem to do better than this. Its performance was...less than great. So go do me proud.

