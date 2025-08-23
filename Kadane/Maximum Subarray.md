Approach==>
[-2,1,-3,4,-1,2,1,-5,4]
we maintain maxi which represents the maximum sum found so far,and currsum which tells us th sum till the current 
index so far and if it is less than 0 then we reset it to 0
TC:O(n);

class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int maxi=INT_MIN;
        int currsum=0;
        for(int i=0;i<nums.size();i++)
        {
            currsum+=nums[i];
           
            maxi=max(maxi,currsum);
             if(currsum<0)
            {
                currsum=0;
            }
        }
        return maxi;
    }
};
