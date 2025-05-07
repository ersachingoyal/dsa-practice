# Find first and last position

**Problem Link:** [Leetcode- Find first and last position](https://leetcode.com/problems/find-first-and-last-position-of-element-in-sorted-array/description/)

## Solution

```cpp
class Solution {
public:
    int binarySearch(vector<int>& nums, int target, int s, int e, bool isSearchingLeft){
        int index = -1;
        while(s <= e){
            int mid = s + (e - s) / 2;
            if(nums[mid] > target){
                e = mid - 1;
            }else if(nums[mid] < target){
                s = mid + 1;
            }else{
                index = mid;
                if(isSearchingLeft){
                    e = mid - 1;
                }else{
                    s = mid + 1;
                }
            }
        }
        return index;
    }

    vector<int> searchRange(vector<int>& nums, int target) {
        vector<int> ans = {-1, -1};
        int s = 0;
        int e = nums.size() - 1;

        int left = binarySearch(nums, target, s, e, true);
        int right = binarySearch(nums, target, s, e, false);

        ans[0] = left;
        ans[1] = right;

        return ans;
    }
};