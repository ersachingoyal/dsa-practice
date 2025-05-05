# Find the Common in 3 Sorted Arrays

**Problem Link:** [GFG- Find the Common in 3 Sorted Arrays](https://www.geeksforgeeks.org/problems/common-elements1132/1)


## Solution

```cpp
class Solution {
  public:
    // Function to find common elements in three arrays.
    vector<int> commonElements(vector<int> &arr1, vector<int> &arr2,
                               vector<int> &arr3) {
        // Code Here
        int i = 0, j = 0, k = 0;
        vector<int> ans;
        
        while(i < arr1.size() && j < arr2.size() && k < arr3.size()){
            if(arr1[i] == arr2[j] && arr2[j] == arr3[k]){
                ans.push_back(arr1[i]);
                i++, j++, k++;
            }else if(arr1[i] < arr2[j] && arr1[i] < arr3[k]){
                i++;
            }else if(arr2[j] < arr3[k]){
                j++;
            }else{
                k++;
            }
            
            while(i > 0 && i < arr1.size() && arr1[i] == arr1[i - 1]) i++;
            while(j > 0 && j < arr2.size() && arr2[j] == arr2[j - 1]) j++;
            while(k > 0 && k < arr3.size() && arr3[k] == arr3[k - 1]) k++;
        }
        
        return ans;
    }
};