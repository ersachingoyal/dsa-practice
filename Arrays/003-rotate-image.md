# Rotate Array

**Problem Link:** [LeetCode- Rotate Image](https://leetcode.com/problems/rotate-image/)

## Approach
For this problem, we have first transposed the matrix, means converted into each row into column and vice versa, after then we have just reversed each row.

## Solution

```cpp
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {

        //transpose
        for(int i = 0; i < matrix.size(); i++){
            for(int j = i; j < matrix[i].size(); j++){
                swap(matrix[i][j], matrix[j][i]);
            }
        }

        //reverse each row
         for(int i = 0 ; i < matrix.size(); i++){
            reverse(matrix[i].begin(), matrix[i].end());
        }
    }
};