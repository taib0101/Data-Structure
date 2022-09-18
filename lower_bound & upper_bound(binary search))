//I seek refuse with Allah, from the accursed devil
//In the name of Allah, the entirely merciful, the specially merciful
#include<bits/stdc++.h>
using namespace std;

void sortt(int l,int r,int *ar)
{
    if(l == r)
        return;
    int mid = (l+r) / 2;
    sortt(l,mid,ar);
    sortt(mid+1,r,ar);
    int temp[r+10];

    for(int i = l,j = mid+1,k = l; k <= r; ++k)
    {
        if(i == mid+1)
            temp[k] = ar[j++];
        else if(j == r+1)
            temp[k] = ar[i++];
        else if(ar[i] > ar[j])
            temp[k] = ar[j++];
        else
            temp[k] = ar[i++];
    }
    for(int i = l; i <= r; ++i)
        ar[i] = temp[i];
    return;
}

int lower_boundd(int l,int r,int x,int ar[])
{
    int y = -1;
    while(l <= r)
    {
        int mid = (l + r) / 2;
        //cout << "l = " << l  << " , r = " << r << endl;
        if(x < ar[mid])
            r = mid - 1;
        else if(x > ar[mid])
            l = mid + 1;
        else
        {
            r = mid - 1;
            y = mid;
            //cout << "y = " << y << endl;
        }
    }
    if(y != -1)
        return y;
    return l;
}

int upper_boundd(int l,int r,int x,int ar[])
{
    int y = -1;
    while(l <= r)
    {
        int mid = (l + r) / 2;
        if(x < ar[mid])
            r = mid - 1;
        else if(x > ar[mid])
            l = mid + 1;
        else
        {
            y = mid;
            l = mid + 1;
        }
    }
    if(y != -1)
        return y+1;
    return l;
}

int main()
{
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
    int t;
    cin >> t;
    while(t--)
    {
        int n;
        cin >> n;
        int ar[n+10] = {0};
        for(int i = 1; i <= n; ++i)
            cin >> ar[i];
        sortt(1,n,ar);
        cout << "After sort --->> " << endl;
        for(int i = 1; i <= n; ++i)
            cout << ar[i] << " ";
        cout << endl;
        int q;
        cin >> q;
        while(q--)
        {
            int x;
            cin >> x;
            int ll = lower_boundd(1,n,x,ar);
            int uu = upper_boundd(1,n,x,ar);
            //int uu = upper_boundd(1,n,x);
            printf("lower_bound[%d] = %d\n",ll,ar[ll]);
            printf("upper_bound[%d] = %d\n",uu,ar[uu]);
        }
    }
    return 0;
}
