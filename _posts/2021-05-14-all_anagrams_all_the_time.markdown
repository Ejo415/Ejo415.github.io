---
layout: post
title:      "All anagrams all the time"
date:       2021-05-14 20:37:34 +0000
permalink:  all_anagrams_all_the_time
---


Ok back to the problem solving. So for the next few weeks Im going to give a problem, and walk through a solution for it step by step. It may not be the best solutions for the problem but it WILL be the one I used. So as long as you're already primed for dissappointment lets get going. 

Our problem this week is.

```
Given two strings, write a function to determine if the second string is an anagram of the first, An anagram is a word, phrase or name formed by rearranging the letters of another. Such as cinema formed from iceman.

```

Ok.

So.

Got it?

Lets break it down. (for the sake of simplicity we will be using one word strings so no whitespacing or extra characters)

```
function validAnagram() {

//first we'll need to set some empty variables to hold the breakdown of each string

//second we'll want to examine each string and break down its contents into the two variables we just made

//after that we'll want to compare the two strings

//lastly we return true or false based on whether both words are an anagram of eachother 

}
```

First things first. name it and plug in the variables you want for the input. Also ive added a little if statement that automatically returns false if the two strings arent the same length.

```
function validAnagram(str1, str2) {
if (str1.length !== str2.length) {
     return false;
   }
```
After that we'll initialize the two variables we'll use to compare to each other at the end.

```
let word1 = {};
  let word2 = {};
	```
Original I know

Next we'll loop over the two words seperately using for/of loops, and for each letter it will look into the variables to see if it already exists. If it doesnt it will initialize a count at oneand if it does it will increment it up by 1.

```
for (let letter of str1) {
    word1[letter] = (word1[letter] || 0) + 1;
  }
  for (let letter of str2) {
    word2[letter] = (word2[letter] || 0) + 1;
  }
```

Finally we're going to use a for/in loop to go through `word1` looking at and comparing its keys to `word2`. If the keys don't match it will return false, if they do it will return true.

```
for (let key in word1) {
    if (word1[key] !== word2[key]) {
      return false;
    }
  }
  return true;
}
```
So at the end of all of that the final soltuion looks like this.

```
function validAnagram(str1, str2) {
  if (str1.length !== str2.length) {
    return false;
  }
  let word1 = {};
  let word2 = {};
  for (let letter of str1) {
    word1[letter] = (word1[letter] || 0) + 1;
  }
  for (let letter of str2) {
    word2[letter] = (word2[letter] || 0) + 1;
  }

  for (let key in word1) {
    if (word1[key] !== word2[key]) {
      return false;
    }
  }
  return true;
}
```

and if true will output the following

```
 validAnagram("iceman", "cinema")
 {i: 1, c: 1, e: 1, m: 1, a: 1, …}
 {c: 1, i: 1, n: 1, e: 1, m: 1, …}
 
true
```

and if false

```
validAnagram("icecan", "cinema")
 {i: 1, c: 2, e: 1, a: 1, n: 1}
 {c: 1, i: 1, n: 1, e: 1, m: 1, a: 1}
 
false
```

And thats it. As I said it might not be the cleverist solution but its the one I used. I'll encourage everyone to find a better one. 

Till next week.






