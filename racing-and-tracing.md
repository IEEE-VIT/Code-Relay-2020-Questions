# Racing and Tracing

**Problem Statement**  

Ansh and Soham are best friends who like participating in  healthy competitions. This time they decided to compete in a race. Initially they both start from the same position. Ansh and Soham move at a constant rate covering **p**  and **q** steps every second respectively. While doing so they leave their footprints behind at their respective locations. The race is **N** meters long. It is guaranteed that **N** is greater than both **p** and **q** . Now after finishing the race , they are wondering , what is the maximum difference between any two consecutive footprints for the entire race track . Help them figure out.


**Input Format**  
- First line contains the number of testcases **T**
- Each testcase conatins three space separated positive integers **p, q, N**

**Constraints**  
- 1< T < 100
- 1 < p,q < 10^9
- 1 < N < 10^9


**Output Format**  
The maximum difference between any two consecutive footprints.

**Difficulty Level**  
Easy
___
**Solution**
~~~
for _ in range(int(input())):
    p,q,n=map(int,input().split())
    print(min(p,q))
~~~