# Find the Disappeared Numbers 

**Problem Link:** [LeetCode- Find the Disappeared Numbers](https://leetcode.com/problems/find-all-numbers-disappeared-in-an-array/description/)


## Solution

```cpp
class Solution {
public:
    vector<int> findDisappearedNumbers(vector<int>& nums) {
        vector<int> ans;   
        for(int i = 0; i < nums.size(); i++){
            int index = abs(nums[i]);
            if(nums[index - 1] > 0){
                nums[index - 1] *= -1;
            }
        }

        for(int i = 0; i < nums.size(); i++){
            if(nums[i] > 0){
                ans.push_back(i + 1);
            }
        }

        return ans;
    }
};