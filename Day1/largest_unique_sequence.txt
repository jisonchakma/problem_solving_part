#include<bits/stdc++.h>
using namespace std;
int main()
{
    int n,k;
    cin>>n>>k;
    string s;
    cin>>s;
    int i=0,j=0,ans=-1,unique=0;
    int freq[26]={0};
    while(j<n)
    {
        char ch=s[j];
        if(freq[ch-'a']==0)
        unique++;
        freq[ch-'a']++;
        if(unique>k)
        {
            while(unique>k)
            {
                char left=s[i];
                freq[left-'a']--;
                if(freq[left-'a']==0)unique--;
                i++;
            }
        }
        if(unique==k)
        {
            ans=max(ans,j-i+1);
        }
        j++;

    }
    cout<<ans<<endl;
    return 0;
}