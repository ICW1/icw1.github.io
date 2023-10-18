---
layout: post
published: True
title: PLACEHOLDER - Cracking the Cryptic - Hypothesis Testing
---

## Intro

Cracking the Cryptic is a [youtube channel](https://www.youtube.com/@CrackingTheCryptic) hosted by sudoku aficionados Mark Goodliffe and Simon Anthony. This channel, and the puzzles contained therein, provide endless ~~distraction~~ entertainment for myself and many others. The pair take turns to solve complex sudokus with abstract rulesets beyond the norm. The puzzles they solve are made by setters from within the sudoku community.  

Due to the hosts' entertainment factor, there are multiple ongoing themes. Namely, Mark's _Goodliffe-ing_ of pencil marks and Simon's enthusiasm for colouring. But, perhaps the most famous gag, is **_the Three in the Corner_**. Whenever the number 3 appears in any of the four corner cells of the sudoku. Viewer's are treated to a sing-song to the tune of R.E.M.'s [_Losing My Religion_](https://www.youtube.com/watch?v=xwtdhWltSIg) except:  

_That's me in the corner, that's me in spotlight, losing my religon_  
becomes:  
_That's **three** in the corner, that's **three** in spotlight, **proving its position**_  

Truly genius...  

As a data scientist. Who's job it is to answer questions which absolutely no-one ever wants answered. I would like to know:
1. For sudokus in general: At what rate would we _expect_ to observe a three in the corner?
2. Does this occur more often in cracking the cryptic sudokus?
3. If so, does that mean setters **like** Simon and Mark's singing...?

Whilst I will leave the final question to you the reader. We can use a statistical hypothesis test to better understand the rest...  

### The maths

Let _a, b, c, d_ denote the digits in the top-left, top-right, bottom-left, bottom-right corners, respectively. Normal Sudoku rules give the following constraints:  

$$ a \ne b, a \ne c, b \ne d, c \ne d $$  

where  

$$ a,b,c,d \in \mathbb{N}_{[1,9]} $$  

To work out the probability of a 3-in-the-corner we need to count all valid combinations of corner digits (the above) and then the number of those which include a three in the corner.

### The data

### The test