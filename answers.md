# CMPS 2200 Assignment 4
## Answers

**Name:** Nahema Dumonteil

Place all written answers from `assignment-04.md` here for easier grading.


**1 Quicksort probabilities**

QQUESTIONS 1 THROUGH 2 ARE ON SEPARATE PDF

- **1a. (5 pts)** What is the probability that Quicksort does $\Omega({n^2})$
  comparisons? 




- **1b. (5 pts)** What is the probability that Quicksort does $10^c n \lg n$
comparisons, for a given $c>0$? What does this say about the
deviation of the actual work from the expected work for Quicksort?


**2 From "Maybe" to "Definitely"**

- **2a. (10 pts)** Give an algorithm to improve the guaranteed success probability and state its work.




- **2b. (6 pts)** Show how to convert $\mathcal{A}$ into an
  algorithm that always produces the correct result, but has an
  expected runtime that depends on $w(n)$ and a success probability
  $\epsilon$.

**3 Determinism versus Randomization in Quicksort**


- **3b. (8 pts)** Compare running times using `compare-qsort` between variants of
Quicksort and the provided implementation of selection sort (`ssort`).

Random schuffle commented out: 
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % /usr/local/bin/python3 /Users/nahe
madumonteil/Documents/Algorithms_Recitation/Assignment_04/main.py
|   n |   ssort |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|---------|---------------------|----------------------|
| 100 |   0.113 |               0.573 |                0.128 |
| 200 |   0.369 |               2.144 |                0.410 |
| 400 |   1.618 |               8.046 |                0.972 |
| 800 |   5.725 |              29.522 |                1.234 |
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 %  

Random shuffle on:
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % /usr/local/bin/python3 /Users/nahe
madumonteil/Documents/Algorithms_Recitation/Assignment_04/main.py
|   n |   ssort |   qsort-fixed-pivot |   qsort-random-pivot |
|-----|---------|---------------------|----------------------|
| 100 |   0.126 |               0.107 |                0.123 |
| 200 |   0.446 |               0.248 |                0.269 |
| 400 |   2.118 |               0.539 |                0.586 |
| 800 |   7.600 |               1.224 |                1.399 |
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % 

comparing asymtomatic bounds:
ssort looks like a O(n^2) growth for both cases. The fixed pivot got better when we randomized the order of the list. With the sorted list it has an O(n^2) growth and with the random list it went down to what it seems O(nlogn). For the qsort random pivot, it stayed consistent, O(nlogn) for both cases. 

Input type: 
using a fixed pivot like the furst element cna introduce a scenario where the recursion tree grows linearly instead of logarithmically, when randomizing the pivot it reduces this risk. Using a random pivot gave us consistent results no matter the input. 



- **3c. (8 pts)** Compare the fastest of your sorting implementations to the Python sorting function `sorted`, conducting the tests in 3b above. 

no shuffle:
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % /usr/local/bin/python3 /Users/nahe
madumonteil/Documents/Algorithms_Recitation/Assignment_04/main.py
|   n |   ssort |   tim_sort |   qsort-random-pivot |
|-----|---------|------------|----------------------|
| 100 |   0.109 |      0.002 |                0.128 |
| 200 |   0.367 |      0.001 |                0.267 |
| 400 |   1.596 |      0.019 |                0.605 |
| 800 |   5.724 |      0.005 |                1.234 |
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % 

Shuffle: 
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % /usr/local/bin/python3 /Users/nahe
madumonteil/Documents/Algorithms_Recitation/Assignment_04/main.py
|   n |   ssort |   tim_sort |   qsort-random-pivot |
|-----|---------|------------|----------------------|
| 100 |   0.128 |      0.009 |                0.133 |
| 200 |   0.437 |      0.016 |                0.260 |
| 400 |   2.133 |      0.036 |                0.625 |
| 800 |   7.591 |      0.078 |                1.302 |
nahemadumonteil@Nahemas-MacBook-Air Assignment_04 % 

Both tim_sort and random pivot are consistent in both cases, but tim_sort is a lot faster. Especially when there is no shuffling for the input list. It is below O(nlogn) maybe even O(n) for when the input is not suffled. Even when it is shuffled, it's safe to say its Big O is O(nlogn). 