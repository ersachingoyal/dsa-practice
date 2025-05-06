# Remove duplicates for sorted array

**Problem Link:** [Leetcode- Remove duplicates for sorted array](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

## Solution

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int i = 0, j = 1;
        while(j < nums.size()){
            if(nums[i] == nums[j]){
                j++;
            }else{
                i++;
                swap(nums[i], nums[j]);
                j++;
            }
        }
        return i + 1;
    }
};