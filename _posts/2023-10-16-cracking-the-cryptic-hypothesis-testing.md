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

#### Counting ALL possibilities of corner digits.
For the first digit _a_ we have nine possibilities, i.e. the digits 1 to 9. For both _b_ and _c_ we have 8 choices of digits, the digits 1 to 9 with whatever digit _a_ is removed. For _d_, we have either 7 or 8 choices for the final digit depending on whether $$b \ne c$$ or $$b=c$$.  

$$\begin{bmatrix}a & b\\c & d\end{bmatrix}$$  

Case 1. $$b \ne c$$. We have:
- 9 choices for _a_
- 8 choices for _b_ (not _a_)
- 7 choices for _c_ (not _a_ not _b_)
- 7 choices for _d_ (not _b_ not _c_)

$$ 9 \times 8 \times 7 \times 7  = 3528 $$  

Case 2. $$b = c$$. We have:
- 9 choices for _a_
- 8 choices for _b_ (not _a_)
- 1 choice  for _c_ (as $b = c$)
- 8 choices for _d_ (not _b_)

$$ 9 \times 8 \times 1 \times 8  = 576 $$  

Total (All possibilities):

$$ 3528 + 576 = 4104 $$

There are 4104 different possibilities for the corner digits under typical sudoku constraints.

#### Counting only occurrences of a _three in the corner_ [TIT-C]
Let $$a=3$$. 
Case 1. There is only one TIT-C, $$d \ne 3$$. We have:

$$\begin{bmatrix}3 & b\\c & d\end{bmatrix}$$

Case 1-1. $$b \ne c$$. We have:
- 1 choice for _a_ (3)
- 8 choices for _b_ (not 3)
- 7 choices for _c_ (not 3 not _b_)
- 6 choices for _d_ (not 3 not _b_ not _c_)
- 4 ways to do this because of rotational symmetry (any of _a,b,c,d_ could be the 3)

$$ 1 \times 8 \times 7 \times 6 \times 4 = 1344 $$  

Case 1-2. $$b = c$$. We have:
- 1 choice for _a_ (3)
- 8 choices for _b_ (not 3)
- 1 choice for _c_ (as $$b = c$$)
- 7 choices for _d_ (not 3 not _b_)
- 4 ways to do this because of rotational symmetry (any of _a,b,c,d_ could be the 3)

$$ 1 \times 8 \times 1 \times 7 \times 4 = 224 $$  

Case 2. There are two TIT-Cs, $$d = 3$$. We have:

$$\begin{bmatrix}3 & b\\c & 3\end{bmatrix}$$

Case 2-1. $$b \ne c$$. We have:
- 1 choice for _a_ (3)
- 8 choices for _b_ (not 3)
- 7 choices for _c_ (not 3 not _b_)
- 1 choices for _d_ (3)
- 2 ways to do this because of rotational symmetry (either _a,c_ or _b,d_ could be the 3s)

$$ 1 \times 8 \times 7 \times 1 \times 2 = 112 $$  

Case 2-2. $$b = c$$. We have:
- 1 choice for _a_ (3)
- 8 choices for _b_ (not 3)
- 1 choice for _c_ (as $$b = c$$)
- 1 choice for _d_ (3)
- 2 ways to do this because of rotational symmetry (either _a,c_ or _b,d_ could be the 3s)

$$ 1 \times 8 \times 1 \times 1 \times 2 = 16 $$  

Total (TIT-Cs):  

$$ 1344 + 224 + 112 + 16 = 1696 $$

#### Probability
We have:  

$$ P(TIT\-C) = (number of corner combinations with a  3 in the corner) / (number of all corner possibilities) $$  

Thus:  

$$ P(TIT\-C) = 1696 / 4104 \approx 0.4133 $$



### The data

Thanks to reddit users [SirJefferE](https://www.reddit.com/r/crackingthecryptic/comments/10fnp0m/3_in_the_corner_cracking_the_cryptic_origin/j4yaoie/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button) and [Same_Historian1922](https://www.reddit.com/r/crackingthecryptic/comments/rwbh8c/does_anyone_know_how_the_3_in_the_corner_meme/jvvnpoc/?utm_source=share&utm_medium=web3x&utm_name=web3xcss&utm_term=1&utm_content=share_button). We know the first utterance of the TIT-C gag was in [this video](https://www.youtube.com/watch?v=_NUlaltMzYY), which was released on 2021/02/04. Also that a while later sudoku setter Matyas Martinka themed a [puzzle](https://www.youtube.com/watch?v=PK3RWVx3tpk) directly on the TIT-C phenomena, 2022/04/24. These dates will form the start of our data collection.



### The test