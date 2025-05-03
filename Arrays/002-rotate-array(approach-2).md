# Rotate Array

**Problem Link:** [LeetCode- Rotate Array](https://leetcode.com/problems/rotate-array/)

## Approach
Without creating a new array
Lets say the array is [1,2,3,4,5,6,7] and k is 3, then after 3 rotation the array is [5,6,7,1,2,3,4] so we can see here that the lst 3, i.e k elements are moved to the start. So here if we reverse the whole array in starting we will have [7,6,5,4,3,2,1], now if we reverse only the first k elements, now the array will be [5,6,7,4,3,2,1] and finally we can reverse the elements left i.e from kth index so final array will be[5,6,7,1,2,3,4]
---

## Solution

```cpp
class Solution {
public:
    void reverse(vector<int>&nums, int i, int j){
        while(i < j){
            swap(nums[i], nums[j]);
            i++;
            j--;
        }
    }

    void rotate(vector<int>& nums, int k) {
        k = k % nums.size();
        reverse(nums, 0, nums.size() - 1);
        reverse(nums, 0, k - 1);
        reverse(nums, k, nums.size() - 1);
    }
};