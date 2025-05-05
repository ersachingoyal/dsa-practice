# Find the Duplicate Number

**Problem Link:** [LeetCode- Find the Duplicate Number](https://leetcode.com/problems/find-the-duplicate-number/description/)


## Solution

```cpp
class Solution {
public:
    int findDuplicate(vector<int>& nums) {
        for(int i = 0; i < nums.size(); i++){
            int index = abs(nums[i]);
            if(nums[index] < 0){
                return index;
            }
            nums[index] *= -1;
        }
        return -1;
    }
};