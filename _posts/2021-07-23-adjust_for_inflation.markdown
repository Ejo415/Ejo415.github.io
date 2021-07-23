---
layout: post
title:      "Adjust for inflation"
date:       2021-07-23 13:14:41 +0000
permalink:  adjust_for_inflation
---


Alrighty, time for another easy leetcode question. This time we're tackling something called "Best Time to Buy and Sell Stock" short and to the point, I know. Anyway heres the question.

> You are given an array prices where prices[i] is the price of a given stock on the ith day.
> 
> You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.
> 
> Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.
> 

OK so.

What we want to do is find the smallest price in the array where we would buy and then find the highest price which would be our selling point and return the difference, or in our case the maxProfit.

First, we want to set up the function (with an argument of an array called prices) and two variables. 

`minBuyPrice` which is set to inifinity so no matter what the first number we examine is it will be smaller. The second is out `maxProfit` which is set to 0.

```
var maxProfit = function(prices) {
    let minBuyPrice = Infinity;
    let maxProfit = 0
```

Next we set up our for loop (a for of loop to be precise) and set an if statement so that for each loop of the array we compare the current price to the minBuyPrice, if it is smaller than minBuyPrice then minBuyPrice is set to the current price.
    
    for (let price of prices){
        if (price < minBuyPrice){
            minBuyPrice = price
						
Then on the next loop if the price is not smaller than the current minBuyPrice we check to see if the difference between the price and the current minBuyPrice is larger than the current maxProfit, if it is we set maxProfit to the new higher value and move down the loop.

        } else if (price - minBuyPrice > maxProfit) {
            maxProfit = price - minBuyPrice
        }
    }
		
Then at the end we just return the maxProfit variable.
    
    return maxProfit
};

altogether we've got 

```
var maxProfit = function(prices) {
    let minBuyPrice = Infinity;
    let maxProfit = 0
    
    for (let price of prices){
        if (price < minBuyPrice){
            minBuyPrice = price
        } else if (price - minBuyPrice > maxProfit) {
            maxProfit = price - minBuyPrice
        }
    }
    
    return maxProfit
};
```

Not super complicated but it could be tricky enough to jam you up. 

And please, by all means get on leetcode and do better than I did. Go through ALL of leetcode, get that job.

Till next week.
