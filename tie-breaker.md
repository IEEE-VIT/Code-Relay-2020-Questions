# Tie-Breaker

**Problem Statement**  

Max is the best coder in the university. His university is organizing the Code-Relay coding contest. Being a member of coding club, He is given responsibility to set a tie-breaker problem for the contest.

Soham also took part in the contest and solved all the problems except Max’s Tie-Breaker problem.

In order to win the contest, Soham has to solve all the problems. Soham was having hard time solving it.

He hopes you can help him. The problem is:

For a given **n**, find the number of pairs **(X, Y)** from the set :
{ nC0, nC1, …………………….., nCn } where  nCr = n!/r!(n-r)! and **X = nCi, Y = nCj (i ≠ j)** such that the given expression(E) results in an even number.

**E = (((X & Y) Ꚛ (X | Y)) & (X Ꚛ Y))**

Where &, |, Ꚛ are the bitwise operators AND, OR and XOR respectively.


**Input Format**  
- First line contains **T**, the number of test cases. 
- Next T lines contain one integer per line, denoting **n**.

**Constraints**  
- 1 ≤ T ≤ 10^5
- 1 ≤ n ≤ 10^9

**Output Format**  
For each test case, output a single integer representing the number of pairs that result in even number based in the given expression.

**Difficulty Level**  
Hard
___
**Solution**
~~~
for _ in range(int(input())):
    n=int(input())
    x=bin(n)
    c=x.count('1')
    o=2**c
    p=o*(o-1)
    p=p>>1
    e=(n+1)-o
    q=e*(e-1)
    q=q>>1
    print(p+q)
~~~