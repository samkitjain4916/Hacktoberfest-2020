                    //Author -> Samkit Jain\\
                      
                      
problem link - https://www.codechef.com/OCT20B/problems/POSAND                      
                  
problem name - POSAND.
                      
                      
                      
#include<bits/stdc++.h>
using namespace std;
#define ll long long int 

int sort(const void *a,const void *b) //qsort(x,n,sizeof(ll),sort);
{
    return(*(ll*)a - *(ll*)b);
}  
int gcd(ll a,ll b)          
{
    ll a1,b1;
    if(b!=0)
    {
        a1=b;
        b1=a%b;
        gcd(a1,b1);
    }
    else
    {return a;}
}
int binary(ll n)
{
    ll binary=0,temp=1;
    while(n>0)
    {
        binary=binary+((n%2)*temp);
        n=n/2;
        temp=temp*10;
    }
    return binary;
}
int no_of_bits(ll n)
{
    return (int)log2(n)+1;
}
int check(ll n)
{
    for(ll i=1;i<=17;i++)
    {
        if(n==pow(2,i))
        {
            return 1;
        }
    }
    return 0;
}


int main() 
{
    ll t;
	cin>>t;
    for(ll test=1;test<=t;test++)
    {
        ll n;
        cin>>n;
        ll sure=check(n);
        ll x[n+1];
        
        if(n==1)
        {
            cout<<1<<endl;
            continue;
        }
        x[1]=2;
        x[2]=3;
        x[3]=1;
        if(sure==0)
        {
            for(ll i=4;i<=n;i++)
            {
                ll sure1=check(i);
                if(sure1==1)
                {
                    x[i]=i+1;
                    x[i+1]=i;
                    i++;
                }
                else
                {
                    x[i]=i;
                }
            }
            
            
            
            
            for(ll i=1;i<=n;i++)
            {
                cout<<x[i]<<" ";
            }
            cout<<endl;
            
        }
        else
        {
            cout<<"-1"<<endl;
        }
        
        
    }
	return 0;
}




