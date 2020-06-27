# hello-world
just another repository
#include<string>
#include <iostream>
#include <cstdio>
#include <cstring>
#include<stack>
#include<vector>
using namespace std;
string pre,mid;
vector<char>post;
void solve(int start1,int end1,int start2,int end2)
{
    if (end1<start1)
        return;
    post.push_back(pre[start1]);
    int q=0;
    while (pre[start1]!=mid[q]) q++;
    int cnt=q-start2;
    solve(start1+1,start1+cnt,start2,q-1);
    solve(start1+cnt+1,end1,q+1,end2);
}
int main()
{
    while (cin>>pre>>mid)
    {
        post.clear();
        solve(0,(int)pre.size()-1,0,(int)mid.size()-1);
        for (int i=(int)post.size()-1;i>=0;i--)
            cout<<post[i];
        printf("\n");

    }
    return 0;
}
//
