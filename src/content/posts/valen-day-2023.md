---
title: Valentine's Day Contest Editorial 2023
description: Valentine's Day Contest on codebreaker.xyz
tags: [contest, editorial]
author: blackscreen1
draft: false
publishedDate: 2023-02-24
updatedDate: 2023-02-24
---

## Preface

_For those people who had no better thing to do on February the 14th_

![](https://preview.redd.it/megamind-no-bitches-meme-3264x3264-v0-gb5bw6safuu81.png?width=1080&crop=smart&auto=webp&s=d1b5b7f7dccdc206c7361a25f5af84fdd30d54b8)

AC count: <br />
xorsplit: 2, including 2 authors <br />
motest: 15, including author

## xorsplit

### Abridged problem statement

The score of a group is defined as the XOR of all of its elements. You start with an empty list, and are
to handle Q updates. At every update, one of two things will happen:

- 0 X: Add the number X to your list.
- 1 X: Delete the number X from your list. It is guaranteed that X had been previously added.

After every update, split the integers into 2 groups such that the sum of the scores of the groups is
maximised. Output this after every update.

### Problem inspiration

This problem was initially intended to be for EC³'s CP training final contest.
However, we only found that the problem was EE after being unable to solve it and asking pavement, who gave a
$\frac{N log^3{A}}{64}$ solution. After consulting zane and maomao90, we figured out a $N log(A)$ solution, allowing
maomao90 to buff the problem.

### Simplified problem

Let's try to solve the problem at a single time unit. Note that for each bit, there are 2 cases:

- The bit appears an odd number of times, and will always contribute its value to the final score.
- The bit appears an even number of times, and will contribute either twice of its value or nothing to the final score.

After processing the first type of bits, we are left with N numbers, each bit appearing an even number of times, trying to find a selection of numbers that maximises
the sum of the bits that can contribute twice. $$N log{A}$$ using xor basis.

### Final solution

Note how we can consider the operation that does the simplified problem as a data structure. We can implement additions and deletions with an additional log factor
using DnC. This method is very classic and is left as a problem for the reader.

Time complexity: $$Q log{Q}(log{Q} + log{X})$$
