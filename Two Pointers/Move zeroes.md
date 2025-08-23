Approach==>
We take a variable pos=0; and we keep iterating the array as we keep finding non zero element 
we keep updating the array in place with the non zero elements increasing pos as we go 
and then then update the remaining elememts with zero 
eg:
Input: nums = [0,1,0,3,12]
Output: [1,3,12,0,0]
arr[0]=1;
then we increase 0 by 1 so now arr[1]=3 and we increase 1 by 1 so now arr[2]=12 ;
for elements having index from 3 to arr.size() we replace the elements by zero;
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int pos=0;
        for(int i=0;i<nums.size();i++)
        {
           if(nums[i]!=0)
           {
            nums[pos]=nums[i];
            pos++;
           } 
        }
        while(pos<nums.size())
        {
            nums[pos]=0;
            
            
            pos++;
        }
        
    }
};

OR
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        if(nums.size()!=1){
      int i=0;
      for(int j=1;j<nums.size();j++)
      {
        if(nums[i]==0 && nums[j]!=0)
        {
            swap(nums[i],nums[j]);
            i++;
        }
        else if(nums[i]!=0 && nums[j]==0)
        {
            i++;
        }
        else if(nums[i]!=0 && nums[j]!=0)
        {
            i++;
        }
        else
        {
            continue;
        }
      }  
        
}
    }
};
