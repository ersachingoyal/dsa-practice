# Maximum Average Subarray

**Problem Link:** [Leetcode- Maximum Average Subarray](https://leetcode.com/problems/maximum-average-subarray-i/description/)

## Solution

```cpp
class Solution {
public:
    double findMaxAverage(vector<int>& nums, int k) {
        double avg = 0;
        double sum = 0;

        for(int i = 0; i < k; i++){
            sum += nums[i];
        }

        avg = sum / k;

        for(int i = 1; i <= nums.size() - k; i++){
            sum = sum - nums[i - 1] + nums[i + k - 1];
            double currAvg = sum / k;
            if(currAvg > avg) avg = currAvg;
        }

        return avg;
    }
};