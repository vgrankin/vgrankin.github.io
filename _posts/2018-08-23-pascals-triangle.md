---
title: "Index by combination using Pascal’s Triangle. How to invent Pascal's Triangle. Combinations with repetition index."
date: 2018-08-23
tags: [pascal triangle, data science, combinations with repetition, 
index by combination, get index by combination, java index by combination, java combination index, 
combination index visual explanation, get combination position, calculate combination index, 
combinations with repetition index, calculate combination index using Pascal Triangle,
 how to create Pascal Triangle, how Pascal's Triangle was invented, Pascal triangle explained, 
 Pascal‘s triangle actual meaning, combinations with repetition to index]
excerpt: "Data Science, Index by combination, Pascal's Triangle"
category: data-science
---

#### Problem statement

Recently I had a requirement to get index for a given combination out of a list of given combinations 
with repetition sequence. 

For example if we have n  = 3 (number of things to choose from) and r = 3 (we choose r of them) 
we have 10 combinations, which means we have the following table:

```
[1, 1, 1]
[1, 1, 2]
[1, 1, 3]
[1, 2, 2]
[1, 2, 3]
[1, 3, 3]
[2, 2, 2]
[2, 2, 3]
[2, 3, 3]
[3, 3, 3]
```

Let’s say I’m interested in combination [2, 2, 2] so looking at table above we can tell it’s index 
is 7 (starting from 1). That was easy, but what if we have n =10, r=10 combinations set? 

Now, according to combinations with repetition formula:

![combinations with repetition formula]({{ site.url }}{{ site.baseurl }}/images/pascal_triangle/combinations_with_repetition_formula.jpg)

$$ \frac {(r + n - 1)!} {r!(n - 1)!}

we need to see a list of 92378 combinations. Of course we can generate all these combinations and 
compare with combination we want to find index of. But it is extremely inefficient and even unreal 
if we have high n and r values (let’s say n=20 and r=20).

So the question is how to find combination’s index just by knowing n, r and combination itself.

#### Here is my investigation and a visual approach to this problem

At first I tried to understand how combinations work and how sequence is produced. Here is for 
example how n=3, r=3 is progressing:


![n=3, r=3 combinations with repetition]({{ site.url }}{{ site.baseurl }}/images/pascal_triangle/pic_1_n=3r=3.jpg)

**Fig. 1.** Here we have all states of let’s call it a “combinations box”. Each box contains 
state. Each state is a combination in that combinations box. Combination is in black color, 
cost of the cell/brick/item movement is in gray. There are 10 possible states.

If we think of the bricks/items movement above in terms of cost we will see that it is cheapest for 
the right-most item to move down and it is more expensive for the items located on the left and it’s 
most expensive to move down for the left-most item (because it always waits until all preceding items 
moved first). 

For example 3rd item (right-most) is moving down effortlessly (step 2 and 3). The price is 1 for 
each movement down.
 
Now to move middle item down (as you can see it moved 1 position down at step 4) we first had to move 
3rd item 2 positions down. So the cost of movement 1 position down for the 2nd item in this case was 2. 

Now if you look at step 6 for example, you will see that second movement down of the 2nd item costs 
1 (not 2 like in first movement case). This is because right-most item could move only 1 brick down 
(because in combinations with repetition any item on the right is >= item on the left, so for example 
we cannot have combination such as [1,2,1] or [2,1,2] etc., only ascending order is allowed).

So for example the total price is 0 at step 1 (no movement was taken)

The total price for step 7 is 6 because 
-	it was necessary to make 3 movements to shift left-most item down (3 because it was 2 shifts down for the right-most item and 1 shift down for the middle one so 3 in total)
-	it was necessary to make 2 movements to shift middle item down (because we first needed to move right-most item 2 positions down to “allow” middle item to move down).
-	and right-most item adds 1 unit of cost as well because it is shifted 1 position down to keep ascending order of the combination

So basically combination’s index is its total cost in that table (cost of preceding movements). If we 
want to start from index 1, we just add 1 to total cost, so index for combination in step 7 will 
be 7 of course.