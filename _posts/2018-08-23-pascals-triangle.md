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

Index by combination using Pascal’s triangle. Get index by combination. Java index by combination. 
Java combination index. Combination index visual explanation. Get combination position. Calculate combination index. Combinations with repetition index. Calculate combination index using Pascal Triangle. How to create Pascal Triangle. How Pascal Triangle was invented. Pascal triangle explained. Pascal‘s triangle actual meaning. Combinations with repetition to index.
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


