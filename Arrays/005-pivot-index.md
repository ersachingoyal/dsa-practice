# Rotate Array

**Problem Link:** [LeetCode- Find Pivot Index](https://leetcode.com/problems/find-pivot-index/description/)


## Solution

```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int totalSum = 0;
        for(int i = 0; i < nums.size(); i++){
            totalSum += nums[i];
        }

        int leftSum = 0;
        int rightSum = 0;

        for(int i = 0; i < nums.size(); i++){
            leftSum += nums[i];
            rightSum = totalSum - leftSum;
            if(leftSum - nums[i] == rightSum){
                return i;
            }
        }

        return -1;
    }
};