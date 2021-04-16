---
layout: post
title:      "Big O of Objects and Arrays (and some super basics for good measure)"
date:       2021-04-16 21:08:49 +0000
permalink:  big_o_of_objects_and_arrays_and_some_super_basics_for_good_measure
---


Alright, this week im gonna go over some basics on Objects and Arrays and then dive into the Big O on some basic actions and methods for each. Lets start with Objects shall we?

Objects are unordered data structures and everything is stored in key : value pairs for example

```
let colors = {
                    Favorite: "Green"
										Least Favorite: "Mauve"
										Dark: "Midnight Blue"
										RGB: ["Red", "Green", "Blue"]
}
```

Now, before the Mauve enthusiasts come at me, stop. Its a dumb color. You're wrong.

Anyway, simple enough. Use want to use Objects for when ou dont need order and you want fast access/insertion and removal.

Now for the Big O of Objects.

Insertion/Removal - O(1) - Constant since you're adding or deleting something specific theres no iteration.
Seaching - O(n) - When searching you're combing through every key/value pair until you find what your looking for.
Access - O(1) - Constant since you're pulling something up specifically with no iteration.

Now for some Object methods

Object.keys, Object.values, Object.entries are all O(n) as it depends how many results exists to be called up.

and

Object.hasOwnPropery is O(1) as it is just searching for a key and returning a boolean in response. 

OK now on to arrays.

Arrays are ORDERED data structures and can contain pretty much anything.

`let insaneArray = ["these", ["can", "hold"], {anything: "you need"}, true, 1]`

is that an insane and probably poor example? Yes. yes it was. but it demonstrates that they can pretty much hold anything. (please never do that). You'll use arrays when you need something to be ordered and you need fast access/insertion and deletion...kind of it depends. Allow me to explan.

Insertion and Removal (push/pop) are O(1) as you are just adding and removing at the end of the Array, no major changes need to be made.

Insertion and Removal (shift/unshift) are O(n) as when you add the front of an array you then need to reorder the whole thing. 

Searching in O(n) - for the same reason it was for Objects. You have to go through the entire thing until you hit on what you're searching for.

Access is O(1) - again for the same reasons as Objects.

Now that that has been handled lets go through the Array methods and the time complexity for them. 

push - O(1)
pop - O(1)
shift - O(n)
unshift - O(n)
concat - O(n)
slice - O(n)
splice - O(n)
sort - O(n * log n)
forEach/map/filter/reduce/etc. - O(n)

First off ill get to why sort looks so damn scary another time. 

Push and Pop we went over

Shift through splice are all O(n) for the same reason in that any changed you make to an array that arent at the end require totally reordering the indexes.

forEach/map/filter/etc are O(n) because it all depends on the size of the arra to begin with.

Thats it for this week. Its all pretty straight forward if, at this point, you have a pretty devent grasp of Big O. 

Till next time kids.


