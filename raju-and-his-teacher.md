# Raju and his Teacher

**Problem Statement**  

Raju bunked the class of his computer science teacher. Being a student with good academic record, the teacher gives him a way out and doesn’t report him to the principal. The teacher gives him a problem. He is not able to solve this problem and thus wants your help in solving it. The problem is that you are given two sequences **A** and **B** of length **N** containing integers. You have to make the sequence **A** same as **B**. The given condition is that you can add or subtract a number **x** to the ith element of **A** to make it equal to the ith element of **B**, only if **x** is a prime number or the sum of prime numbers.

Your job is to print **“YES”** if it is possible to make A equal to B and **“NO”** otherwise.


**Input Format**  
- The first line contains **T** denoting the total number of testcases.
- First line of each testcase contains an integers **N**.
- Second line of each testcase contains  **N** space separated integers, A1, A2, A3, .. ,AN.
- Third line of each testcase contains  **N** space separated integers, B1, B2, B3, .. , BN.


**Constraints**  
- 1 ≤ T ≤ 50
- 1 ≤ N ≤ 10^5
- -10^7 ≤ Ai, Bi ≤ 10^7

Subtask 1 (50 points) :- N ≤ 10^2  
Subtask 2 (100 points) :- Original Constraints


**Output Format**  
For each testcase output “YES” or “NO” (without quotes).

**Difficulty Level**  
Easy
___
**Solution**
~~~
for _ in range(int(input())):
    n=int(input())
    a=list(map(int,input().split()))
    b=list(map(int,input().split()))
    f=1
    for i in range(n):
        if abs(a[i]-b[i])==1:
            f=0
            break
    if f:
        print('YES')
    else:
        print('NO')
~~~