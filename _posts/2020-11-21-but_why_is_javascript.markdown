---
layout: post
title:      "But WHY is Javascript"
date:       2020-11-21 15:10:43 +0000
permalink:  but_why_is_javascript
---



I'm not gonna lie, this one was rough. It all came together in the end but getting there was an adventure of forgetting and remembering everything ive learned so far. Getting the backend up was simple enough. But that frontend was an adventure.

Probably the hardest thing for me to get working was naturally the last thing I had to do to finish the project. What I had to do was get a remove button to work on an object that wasnt explicitly being rendered to the front end from the back. The project is a pantry inventory system and my relationships were as follows. 

```
Kitchens < Inventories > Items

```

With both Kitchens and Items having a has many through relationship with each other.


So what I wound up doing (with some gracious assistance from my classmates) was creating a whole new ` Inventory`    class in the front end with an API fetch solely to get the data and make a function that would determine the `Inventory` object id by inputing the kitchen and item ids into it, which would up looking like this.

```
static findInv(k, i){
     let kNum =  Number.parseInt(k)
     let iNum =  Number.parseInt(i)
   return Inventory.all.find((inv)=>{
        return inv.kitchen_id === kNum && inv.item_id === iNum 
     }).id
    }
}
```

From there it was just a matter of inserting the `kitchen_id` and item id into the HTML elements in a place they would be accessable.

For the `kitchen_id` it was put in the `parentElement`

```
<div class="dropdown-menu" id='${this.id}' aria-labelledby="dropdownMenu2">
```

and for the ` item_id`  it was put on the remove button itself.

```
 ${Pantry.all.map(pantry =>  `<button class="dropdown-item addInvButton"  type="button" id="${pantry.id}">${pantry.name}</button>`).join("")}
```

Figuring out all that took a number of house but it was intensely satisfying when it started to spit out what I wanted it to.

Javascript is a gigantic pain to work with sometimes because its either too finnicky or too free form but when you get it doing what you want its intensely satisfying.
