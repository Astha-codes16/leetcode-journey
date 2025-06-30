https://leetcode.com/problems/count-primes
class Solution {
public:
    int countPrimes(int n) {
         if(n<=1)
    {
        return 0;
    }
    vector<bool>v(n,true);
    v[0]=false;
    v[1]=false;
    int count=0;
   
    for(int i=2;i*i<n;i++)
    {
        if(v[i])
        {
            for(int j=i*i;j<n;j=j+i)
            {
                v[j]=false;
            }
        }
    }
    for(int i=2;i<n;i++)
    {
        if(v[i])
        {
            count++;
        }
    }
    return count;
    }
};
approach==>
for the inner loop we start from j=i*i bcz anthing smaller than i*i is also a multiple of i that would be i*k 
which wouldbe already handled by k
