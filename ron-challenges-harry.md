# Ron challenges Harry

**Problem Statement**  

Ron challenges Harry to find the number of ways to construct an array such that consecutive positions contain different values.

Harry is given a task to construct an array with **n**  elements such that each element is between **1** and **k** inclusive. Also, the first and the last element of the array needs to be **1** and **x** respectively. Harry isn’t good at maths, so he comes to you for help.

Help Harry find the number modulo **10^9 + 7**.


**Input Format**  
- 1 ≤ T ≤ 10
- 3 ≤ n ≤ 10^5
- 2 ≤ k ≤ 10^5
- 1 ≤ x ≤ k

Subtask 1 (30 points) :- n ≤ 10^3  and k ≤ 10^2   
Subtask 2 (150 points) :- Original Constraints


**Constraints**  
- 1< T < 100
- 1 < p,q < 10^9
- 1 < N < 10^9


**Output Format**  
For each testcase output the number of ways to construct the array such that consecutive elements are distinct.

Output your answer modulo 10^9+7.


**Difficulty Level**  
Medium
___
**Solution**
~~~
mod=10**9+7
n,k,x=map(int,input().split())
n-=2
dp=[1]*(n+1)
dp[1]=(k-2)
for i in range(2,n+1):
    p=((k-2)*dp[i-1])%mod
    q=((k-1)*dp[i-2])%mod
    dp[i]=(p+q)%mod
if x!=1:
    print(dp[n])
else:
    print((dp[n-1]*(k-1))%mod)
~~~