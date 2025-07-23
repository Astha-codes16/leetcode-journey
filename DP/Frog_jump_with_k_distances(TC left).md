class Solution {
public:
   int solve(int i,vector<int>& heights,int k,vector<int>& dp)
    {
if(i==0)
return 0;
if(dp[i]!=-1)
{
    return dp[i];
}
int min_energy=INT_MAX;
for(int j=1;j<=k;j++)
{  
     if((i-j)>=0)
{
    int jump=solve(i-j,heights,k,dp)+abs(heights[i]-heights[i-j]);
     min_energy= min(min_energy,jump); 
    
}
}
return dp[i]=min_energy;
    }
    int frogJump(vector<int>& heights, int k) {
        int h=heights.size();
        vector<int>dp(h,-1);
        int i=heights.size()-1;
        
        return solve(i,heights,k,dp);
    }
};
