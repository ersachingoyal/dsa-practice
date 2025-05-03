# Rotate Array

**Problem Link:** [LeetCode- Rotate Array](https://leetcode.com/problems/rotate-array/)

## Approach
Creating a new array
Lets say the array is [1,2,3,4,5,6,7] and k is 3, then after 3 rotation the array is [5,6,7,1,2,3,4] so we can see in the final array the new indexes are like this, the 0th index element in the original array became the 3rd index element in the final array, the 1st index element in the original array became the 4th index element in the final array. So we can first create a new array of the same size, the loop over the original array and then start filling the positions in the new array based on this formula (i+k)%n, so if i = 0, k is 3 and n is 7, we will get 3 here, so the current 0th element will go to 3rd index in the new array.
---

## Solution

```cpp
class Solution {

public:
    void rotate(vector<int>& nums, int k) {
        int n=nums.size();
        vector<int>temp(n);
        
        for(int i=0;i<nums.size();i++){
            temp[(i+k)%n]=nums[i];
        }
         nums=temp;
    }
};