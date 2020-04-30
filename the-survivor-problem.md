# The Survivor Problem

**Problem Statement**  

A flight has crashed on a mysterious island. After the crash, there were **N survivors**. 

Initially, every survivor was on his own. But soon they realized there are others on that island too.

Now, these **N** survivors want to unite, to protect themselves from any kind of danger which may appear on the mysterious island.

You have to handle **Q** queries; which consist of two survivors becoming friends and thereby uniting their respective groups into a  larger group.

After each query, output the difference between the group of largest size and group of smallest size at that time.

If there is only one group, output 0. At first, everyone is in their own group.

Also note, if the two survivors in the query are already in the  same group, print the current answer, and skip merging groups.



**Input Format**  
- The first line contains **T** denoting the total number of testcases.
- First line of each testcase contains two positive integers **N** and **Q** denoting the number of survivors and queries respectively.
- Next **Q** lines consists of two integers, **A** and **B**, representing that **A** and **B** became friends uniting there groups. 


**Constraints**  
- 1 ≤ T ≤ 10
- 1 ≤ N ≤ 100000
- 1 ≤ Q ≤ 10000


**Output Format**  
For each testcase, output **Q** lines, the answer after each query.

**Difficulty Level**  
Hard
___
**Solution**
~~~
#include<bits/stdc++.h>
using namespace std;
#define lli long long int
#define p_b push_back
#define m_k make_pair
#define ipair pair<lli,lli>
#define mod 1000000007
#define inf INT_MAX
vector<int> a;
int find(int x)
{
    vector<int> p;
    while(x!=a[x])
    {
        p.p_b(x);
        x=a[x];
    }
    for(int i:p)
    {
        a[i]=x;
    }
    return x;
}
int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(0);
    int T;
    cin>>T;
    while(T--)
    {
        int n,q;
        cin>>n>>q;
        a.clear();
        a.resize(n+1);
        map<int,int> mp;
        vector<int> st(n+1);
        int mm=1;
        for(int i=1;i<=n;i++)
        {
            a[i]=i;
            mp[1]++;
            st[i]=1;    
        }
        while(q--)
        {
            int u,v;
            cin>>u>>v;
            int x=find(u),y=find(v);
            u=x;
            v=y;
            if (u!=v)
            {
                a[u]=v;
                mp[st[v]]--;
                if(mp[st[v]]==0) mp.erase(st[v]);
                st[v]+=st[u];
                mp[st[v]]++;
                mp[st[u]]--;
                if(mp[st[u]]==0) mp.erase(st[u]);
                if(st[v]>mm) mm=st[v];
            }
            auto it=mp.begin();
            cout<<mm-it->first<<endl;
        }
    }
    return 0;
}
~~~