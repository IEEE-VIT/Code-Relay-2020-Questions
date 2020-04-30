# Germ Fight

**Problem Statement**  

Soham is studying a new strain of germs. These germs are kept in a set of **N** petri dishes. Each of the dishes can hold **K** germs. Germs are added one by one to the first dish. If **i(th)** dish already has **K** germs and another is added then all the germs will fight each other until only one germ is left and it will be transferred to the **i+1(th)** dish, however if another germ is added to the **N(th)** petri dish when it already has **K** germs all the germs in the **N(th)** dish are killed. Let A1,A2....AN be the number of germs in the 1,2....N(th) petri dishes. Initially all the dishes are empty. You are given **M** number of germs, you have to display A1,A2....AN after all of these germs are added.


**Input Format**  
- The first line of the input contains a single integer **T** denoting the number of test cases. 
- The next T lines would contain a three integers **N,K and M**.


**Constraints**  
- 1 ≤ T ≤ 10
- 1 ≤ N ≤ 100
- 1 ≤ K ≤ 100
- 1 ≤ M ≤ 10^9

Subtask 1 (75 Points) : 1 ≤ M ≤ 10^5    
Subtask 2 (150 Points): Original constraints


**Output Format**  
For each test case, print a single line containing spaced integers A1,A2....AN.

**Difficulty Level**  
Medium
___
**Solution**
~~~
T=int(input())
for _ in range(0,T):
    n,k,m=map(int,input().split())
    L=[]
    for i in range(0,n):
        tt=pow(k+1,i)
        L.append((m//tt)%(k+1))
    print(*L)
~~~