#include<bits/stdc++.h>
using namespace std;
int find(int u,int *arr)
{
    //cout << "arU = " << *(arr+u) << endl;
    if(*(arr+u) == u)
        return u;
    *(arr+u) = find(*(arr+u),arr);
    return *(arr+u);
}
void unionn(int u, int v, int *arr)
{
    int p = find(u,arr);
    int q = find(v,arr);
    if( p != q)
        *(arr+q) = p;
}
int main()
{
    int arr[101];
    // evry node has own parent
    for(int i = 1; i <= 8; ++i)
        arr[i] = i;
    // for(int i = 1; i <= 8; ++i)
        // cout << "child = " << i << ", parent = " << arr[i] << endl;
    int u, v;
    // 7 8
    // 6 7
    // 5 6
    // 4 5
    // 3 4
    // 2 3
    // 1 2
    // 0 0
    while(cin >> u >> v && u && v)
    {
        unionn(u, v, arr);
    }
    while(cin >> u >> v && u && v)
    {
        cout << "child 01 = " << u << ", parent = " << find(u,arr) << endl;
        cout << "child 02 = " << v << ", parent = " << find(v,arr) << endl;
    }
    return 0;
}
