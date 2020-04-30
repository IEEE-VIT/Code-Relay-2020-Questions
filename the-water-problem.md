# The Water Problem

**Problem Statement**  

Maharashtra always faces scarcity of water. A lot of small towns don’t receive adequate water supply. Assume that a particular town has a water reservoir that provides infinite water supply that serves that town first and then the other towns
You are in control of the water distribution of the state. Assuming there are **n** towns which have to be provided with water. Each town has a number **from 0 to n-1**. You are given **k** water-lines to distribute water among the towns, each containing a space separated tuple **i j**, representing a connection between the ith and jth town. Each town has a minimum requirement of water (in litre). You are given an integer representing the id of the town, which has the reservoir. 
A town is served with water only if it is connected to a town j such that **capacity (j) > capacity (i)**. You are required to print **YES** if all towns are supplied with water. Else print **NO**.


**Input Format**  
- The first line contains the number of testcases **T**.
- The first line of each testcase contains the number of towns (n) and their connections (m), separated by a space.
- Then the next line contains the capacity of each town seperated by a space.
- Then the next m lines contain the connection between the ith and jth town.
- Finally, the last line of each test case contains the id of the town which has the reservoir.

**Constraints**  
- 0 < T < 10
- 0 < N < 10^3
- 0 < M < (N*(N-1))/2
- 0 < Capacity of each town < 10^8

**Output Format**  
You are required to print **YES** if all towns are supplied with water.  Else print **NO**.

**Difficulty Level**  
Medium
___
**Solution**
~~~
for _ in range(int(input())):
    n,m=map(int,input().split())
    wt=list(map(int,input().split()))
    ed={}
    for i in range(m):
        u,v=map(int,input().split())
        if u in ed:
            ed[u].append(v)
        else:
            ed[u]=[v]
        if v in ed:
            ed[v].append(u)
        else:
            ed[v]=[u]
    src=int(input())
    vis=[0 for i in range(n)]
    vis[src]=1
    q=[src]
    while(q):
        node=q[0]
        del(q[0])
        if node in ed:
            for i in ed[node]:
                if(wt[i]<wt[node] and vis[i]==0):
                    vis[i]=1
                    q.append(i)
    s=sum(vis)
    if s==n:
        print('YES')
    else:
        print('NO')
~~~