//I seek refused with Allah ,from the accursed devil
//In the name of Allah,the Entirely Merciful, the Specially Merciful
#include<bits/stdc++.h>
using namespace std;
map < int, int > qvalue;
void segmented_tree(int l,int r,int ar[],int node)
{
    int mid = (l + r) / 2;
    if(l == r)
    {
        qvalue[node] = ar[l];
        return;
    }
    segmented_tree(l,mid,ar,node*2);
    segmented_tree(mid+1,r,ar,(node*2) + 1);
    qvalue[node] = qvalue[(node*2)] + qvalue[(node*2) + 1];
}

int query(int node,int l,int r,int x,int y)
{
    if(y < l || r < x)
        return 0;
    if(x <= l && r <= y)
        return qvalue[node];
    int mid = (l + r) / 2;
    int s1 = query(node*2,l,mid,x,y);
    int s2 = query((node * 2) + 1,mid+1,r,x,y);
    cout << "s1 = " << s1 << " s2 = " << s2 << endl;
    return s1 + s2;
}

void Updatee(int node,int l,int r,int x)
{
    if(x < l || r < x)
        return;
    if(l == r)
    {
        int newvalue;
        cin >> newvalue;
        qvalue[node] = newvalue;
        return;
    }
    int mid = (l+r) / 2;
    Updatee(node*2,l,mid,x);
    Updatee((node*2)+1,mid+1,r,x);
    qvalue[node] = qvalue[(node*2)] + qvalue[(node*2) + 1];
}

int main()
{
    int t;
    cin >> t;
    while(t--)
    {
        int n;
        cin >> n;
        int ar[n+10];
        for(int i = 1; i <= n; ++i)
            cin >> ar[i];
        qvalue.clear();
        segmented_tree(1,n,ar,1);
        for(auto it = qvalue.begin(); it != qvalue.end(); ++it)
            printf("qvalue[%d] = %d\n",it->first,it->second);
        cout << "Enter Query Test case : " << endl;
        int tt;
        cin >> tt;
        while(tt--)
        {
            int x, y;
            cin >> x >> y;
            cout << "Query sum = " << query(1,1,n,x,y) << endl;
        }
        cout << "Update any value -- " << endl;
        int a,index;
        cin >> index;
        Updatee(1,1,n,index);
        cout << "After Update value the array will be" << endl;
        for(auto it = qvalue.begin(); it != qvalue.end(); ++it)
            printf("qvalue[%d] = %d\n",it->first,it->second);
    }
    return 0;
}
