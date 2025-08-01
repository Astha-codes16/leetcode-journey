class Solution {
  public:
  int solve(int day,int lastactivity,vector<vector<int>>& arr,vector<int>&dp)
  { int ni=arr.size();
  
    int points=0;
    if(day==ni)
    {
        return 0;
    }
    if(dp[day]!=-1)
    {
        return dp[day];
    }
    int maxpoints=0;
        for(int i=0;i<3;i++)
    {
        if(i!=lastactivity)
        {
            points=arr[day][i]+solve(day+1,i,arr,dp);
        }
        maxpoints=max(points,maxpoints);
    }
    return dp[day]=maxpoints;
    
  }
    int maximumPoints(vector<vector<int>>& arr) {
        int n=arr.size();
        vector<int>dp(n,-1);
        //n= numberr of days
        return solve(0,3,arr,dp);
    }
};
