# COVID 19

**Problem Statement**  

Due to the recent outbreak of COVID-19, the government of India has devised an **N**-day plan. 

During these **N** days, the citizens are not allowed to move out of their houses for more than one consecutive day. Given the number of days **N**, print the number of ways the **N**-day plan can be completed.

Note that it is possible  to not move out of the house on any day at all and still complete the plan.


**Input Format**  
- The first line contains **T** denoting the total number of testcases.
- Each testcase contains a positive integer **N** denoting the number of days. 


**Constraints**  
- 1 ≤ T ≤ 10000
- 1 ≤ N ≤ 10^18  
Subtask 1 (75 points) :- N ≤ 10^3    
Subtask 2 (150 points) :- Original Constraints



**Output Format**  
The output contains **T** lines, one for each test case. Each line contains a positive integer, denoting the number of ways by which the **N**-day plan may be completed.

Output your answer modulo 10^9+7.


**Difficulty Level**  
Medium
___
**Solution**
~~~
def ppow(exp,mod):
    a=[[1,1],[1,0]]
    res=[[1,1],[1,0]]
    while(exp):
        if(exp&1):
            p=res[0][0];
            q=res[0][1];
            r=res[1][0];
            s=res[1][1];
            res[0][0]=(p*a[0][0]+q*a[1][0])%mod;
            res[0][1]=(p*a[0][1]+q*a[1][1])%mod;
            res[1][0]=(r*a[0][0]+s*a[1][0])%mod;
            res[1][1]=(r*a[0][1]+s*a[1][1])%mod;  
        exp=exp>>1
        p=a[0][0];
        q=a[0][1];
        r=a[1][0];
        s=a[1][1];
        a[0][0]=(p*p+q*r)%mod;
        a[0][1]=(p*q+r*s)%mod;
        a[1][0]=(r*p+s*r)%mod;
        a[1][1]=(r*q+s*s)%mod;
    ans=((res[0][0]<<1)+res[0][1])%mod
    return ans
mod=10**9+7
for _ in range(int(input())):
    n=int(input())
    if(n==1):
        print('2')
        continue
    ans=ppow(n-2,mod);
    print(ans)
~~~