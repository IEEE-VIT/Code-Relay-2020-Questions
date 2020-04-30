# Lucky Beans

**Problem Statement**  

Soham likes to carry his lucky beans with him all the time. The weight of the lucky beans is **W** and they consist of **P1** percentage of water. Since he is carrying the lucky beans with him all day long, some amount of water evaporates from the beans. To regain some of the water content he soaks the beans in water. At the end of the day the lucky beans now consist of **P2** percentage of water. Soham now wants to know the new weight of his lucky beans rounded to 2 decimal places.


**Input Format**  
- The first line of the input contains a single integer **T** denoting the number of test cases. 
- The next T lines would contain three spaced integers **W,P1 and P2**.

**Constraints**  
- 1 ≤ T ≤ 10^6
- 1 ≤ W ≤ 10^5
- 0 ≤ P1 ≤ 100
- 0 ≤ P2 ≤ 100
 
Subtask 1 (50 points) :- P2 = 0   
Subtask 2 (100 points) :- Original Constraints

**Output Format**  
For each test case, print a single line containing the new weight of the lucky beans rounded to two decimal places.

**Difficulty Level**  
Easy
___
**Solution**
~~~
t=int(input())
for _ in range(t):
    w,p1,p2=map(int,input().split())
    if(p1==p2):
        ans="{:0.2f}".format(w)
    else:
        ans=((100-p1)*w)/(100-p2)
        ans="{:0.2f}".format(ans)
    print(ans)
~~~