///////////////// Allahu Akbar ///////////////
//////////////Alhamdulillah for everything ////////////////
#include<bits/stdc++.h>
using namespace std;

struct node
{
    int n;
    char c;
    struct node *head;
    struct node *left;
    struct node *right;
};
class cmp
{
    public :
        bool operator () (node xx, node yy)
        {
            return xx.n > yy.n;
        }
};
struct node *huffman(map < char , int > m,int j)
{
    priority_queue < node , vector < node >, cmp > pq;
    for(auto it = m.begin(); it != m.end(); ++it)
    {
        struct node *root = (node *) malloc (sizeof(node));
        root -> n = it -> second;
        root -> c = it -> first;
        root -> left = NULL;
        root -> right = NULL;
        cout << "char = " << it->second << endl;
        cout << "totall = " << it->first << endl;
        pq.push({it->second,it->first,root});
    }
    struct node *hh = NULL;
    while(pq.size() != 1)
    {
        int aa = pq.top().n;
        struct node *r1 = pq.top().head;
        pq.pop();
        int bbb = pq.top().n;
        struct node *r2 = pq.top().head;
        pq.pop();
        struct node *root = (node *) malloc (sizeof(node));
        root -> n = aa + bbb;
        root -> c = '\0';
        root -> left = r1;
        root -> right = r2;
        // cout << "n = " << r1 -> n << endl;
        // cout << "n1 = " << r2 -> n << endl;
        pq.push({aa+bbb,'\0',root});
    }
    hh = pq.top().head;
    //cout << "last = " << hh -> left -> n << endl;
    
    return hh;
}
void show(struct node *h,string ss,char ch)//recursion tree te return age push krle pore pop krar lge na kintu return er pore push krle pop krar lge

{
    if(ch != '\0')//eivabeo hoy
        ss.push_back(ch);
    if(h -> left == NULL && h -> right == NULL)
    {
        cout << "c = " << h -> c << ", code = " << ss << endl;
        return;
    }
    
    //ss.push_back('0');
    show(h->left,ss,'0');
    //ss.pop_back();
   // ss.push_back('1');
    show(h->right,ss,'1');
    //ss.pop_back();
}
//zzccccccaaaaaaaaaaddddddddddddffffffffffffff
int main()
{
    string str;
    while(getline(cin,str))
    {
        int j = 0;
        map < char , int > m;
        for(int i = 0; i < str.size(); ++i)
            m[str[i]]++;
        
        struct node *h = huffman(m,j);
        string ss;
        show(h,ss,'\0');
    }
    return 0;
}
