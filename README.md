# Weighted-Graph-take-input-and-print
#include<bits/stdc++.h>
using namespace std;
int main()
{
    int node,n,edge;
    cin>>node>>edge;
    vector<pair<int,int> > adv[node];
    for(int i=0;i<edge;i++)
    {
        int x,y,z;
        cin>>x>>y>>z;
        adv[x].push_back(make_pair(y,z));
        adv[y].push_back(make_pair(x,z));
    }

    for (int u = 0; u < node; u++)
    {
        int v=0,w=0;
        cout << "Node " << u << " makes an edge with:"<<endl;
        for (auto it = adv[u].begin(); it!=adv[u].end(); it++)
        {
            v = it->first;
            w = it->second;
            cout << "\tNode " << v << " with weight ="
                 << w <<endl;
        }
        cout<<endl;
    }
}

