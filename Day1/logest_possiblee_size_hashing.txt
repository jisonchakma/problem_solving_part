#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n,k;
    cin>>n>>k;
    int ans=0,sum=0;
    vector<int>a(n);
    for(int i=0;i<n;i++)
    {
        cin>>a[i];
    }
    unordered_map<int,int>mp;
    for(int i=0;i<n;i++)
    {
        sum+=a[i];
        if(sum==k)
        {
            ans=max(ans,i+1);
        }
        if(mp.find(sum-k)!=mp.end())
        {
            int idx=mp[sum-k];
            ans=max(ans,i-idx);
        }
        if(mp.find(sum)==mp.end())
        {
            mp[sum]=i;
        }
    }
    cout<<ans<<endl;
    return 0;
}