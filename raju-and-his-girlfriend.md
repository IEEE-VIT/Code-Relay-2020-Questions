# Raju and his girlfriend

**Problem Statement**  

Raju has been happy lately. Raju has recently got a job as an associate for a huge firm and he has also got a girlfriend named Riya. He loves spending time with her. When he is away for work though, she gets worried about him a lot.

She wants Raju to text her **N** times a day. Raju also likes his job and his manager being a little strict, doesn’t allow him to text a lot. Raju’s work time can be divided into maximum of 10^9 slots. He can text him only during a handful number of slots, i.e. **M** slots. He would like the slots during which he texts to be as far away as possible, so that his manager doesn’t think that he is distracted from work. Another rule is that he texts her the first time he gets free, i.e. in the first time slot of his work time.

He is not that good with math and problem solving, thus he needs help from you to solve his problem. He needs you to tell him the minimum time interval gap he would have to wait for him to text her such that the minimum time interval is as large as it can be.



**Input Format**  
- The first line contains **T** denoting the total number of testcases.
- First line of each testcase contains two integers **N** and **M**.
- Second line of each testcase contains **M** space separated integers, T1, T2, T3, .. ,TM . which represents the **distinct slots**.

**Constraints**  
- 1 ≤ T ≤ 10
- 1 ≤ N ≤ M ≤ 10^5
- 1 ≤ Ti ≤ 10^9

**The input/ouput is quite large, please use fast i/o methods.**

**Output Format**  
For each testcase output one integer : the largest minimum time interval.

**Difficulty Level**  
Medium
___
**Solution**
~~~
import math
import sys
hh=10**9
T=int(sys.stdin.readline())
for _ in range(T):
    n,m = map(int,sys.stdin.readline().split())
    arr=list(map(int,sys.stdin.readline().split()))
    arr.sort()
    low =1
    high =hh
    ans =-1
    while(low<=high) :
            mid = low+ int((high-low)/2)
            x =1
            d = arr[1]-arr[0]
            for i in range(1,m):
                    if(d>=mid) :
                            x=x+1
                            if i!=m-1 :
                                    d =arr[i+1]-arr[i]
                    else : 
                            if i!=m-1 :
                                    d = d + arr[i+1]-arr[i]
            if(x>=n) :
                    ans =mid
                    low =mid+1
            else :
                    high = mid-1
    sys.stdout.write(str(ans)+'\n')

~~~