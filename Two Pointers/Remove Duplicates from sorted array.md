approach==>
[1,1,1,2,2,3,3,4,4]
int i=0;
j goes from j=1 till array size;
if arr[j] matches with arr[i] then do not do anything else 
increase i and swap arr[i] and arr[j];
TC:O(n);
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i=0;
        for(int j=1;j<nums.size();j++)
        {
            if(nums[j]!=nums[i])
            {
                i++;
                swap(nums[i],nums[j]);



            }
        }
        return i+1;
    }
};
