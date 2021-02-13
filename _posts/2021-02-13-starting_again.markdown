---
layout: post
title:      "Starting Again"
date:       2021-02-13 22:46:32 +0000
permalink:  starting_again
---


So here we are again, starting fresh.

I graduated in December and now am very firmly in my hunt for employment, and one thing I knew going in but has really been driven home the last few weeks is that the learning never stops, which is fine by me.

First up on my shiny new to-do list is Time Complexity, because they can explain it better than I can ill let Wikipedia give you the cliff notes.

>  In computer science, the time complexity is the computational complexity that describes the amount of computer time it takes to run an algorithm.
>  

so if we have an function like this

```
  function stringIncludes(word, letter){
    let matches;
    for(let i = 0; i < word.length; i++){
      if(word[i] === letter){
        matches = true
      }
    }
    return !!matches
  }
	
	
	
	 stringIncludes("banana", "a")
  // true
  stringIncludes("banana", "d")
  // false
	
```


Using banana as the example we can say that there are 9 steps involved to deterimine if a letter is in the word (the if statement is run for each letter in the string + the other lines of code in the function) and according to the cirriculum

> If let the number of letters in our word be n then we can say our function runs in n + 3 time. So if we choose a string of 100 letters, this takes 100 + 3 = 103 time. We call this the time complexity of the function.
> 

This is all barely scratching the surface of the subject but I'm just getting started. Worst, Best case scenarios and Big O. theres a whole lot that ill write on once I actually manage to get a better handle on it. My learning is clearly far from over.



