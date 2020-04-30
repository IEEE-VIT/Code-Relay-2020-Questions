# Help Spiderman

**Problem Statement**  

To become the "cool kid" of his college, Spiderman wants to buy a lot of things from a nearby store. Iron man gives **M dollars** to Spiderman and asks him to return the remaining unused amount. But, Iron man being the smart person he is, knows that Spiderman will exhaust all the money given to him. To prevent this, Iron man puts a conditions on Spiderman - he can only buy a sequence of consecutive things. Based on this condition, Spiderman wants to return the minimum amount possible. This task seems to be very difficult for Spiderman and hence comes to you for help. Can you help Spiderman return the minimum possible amount back to Iron Man based on the given condition?

**Input Format**  
- The first line contains **T** denoting the total number of testcases.
- First line of each testcase contains two integers **N** and **M**.
- Second line of each testcase contains  **N** space separated integers, X1, X2, X3, .. ,XN . which represents the price of the ith item.


**Constraints**  
- 1 ≤ T ≤ 10
- 2 ≤ N ≤ 10^5
- 1 ≤ M ≤ 10^8
- 1 ≤ Xi ≤ 10^8

Subtask 1 (50 points) :- N ≤ 10^3 and M ≤ 10^3   
Subtask 2 (100 points) :- Original Constraints

**Output Format**  
For each test case, print a single line containing one integer, the minimum possible amount that is to be returned.

**Difficulty Level**  
Easy
___
**Solution**
~~~
for _ in range(int(input())):
    # your code goes here
    n,m=map(int,input().split())
    l=list(map(int,input().split()))
    ans=0
    ss=0
    j=0
    for i in range(len(l)):
        ss+=l[i]
        while(ss>m):
            ss-=l[j]
            j+=1
        if(ss>ans):
            ans=ss
        if(ans==m):
            break
    print(m-ans)
~~~