# Find Peak Index in a mountain array

**Problem Link:** [Leetcode- Find Peak Index in a mountain array](https://leetcode.com/problems/peak-index-in-a-mountain-array/description/)

## Solution

```cpp
class Solution {
public:
    int peakIndexInMountainArray(vector<int>& arr) {
        if(arr[0] > arr[1]) return 0;
        if(arr[arr.size() - 1] > arr[arr.size() - 2]) return arr.size() - 1;

        int s = 1, e = arr.size() - 2, idx = -1;

        while(s <= e){
            int mid = s + (e - s) / 2;
            if(arr[mid] > arr[mid - 1]){
                idx = mid;
                s = mid + 1;
            }else{
                e = mid - 1;
            }
        }

        return idx;
    }
};