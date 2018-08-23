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


