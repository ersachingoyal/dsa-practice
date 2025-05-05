# Find the first repeating element

**Problem Link:** [GFG- Find the first repeating element](https://www.geeksforgeeks.org/problems/first-repeating-element4018/1)


## Solution

```cpp
class Solution {
  public:
    int firstRepeated(vector<int> &arr) {
        // code here
        map<int, int> count;
        
        for(int i = 0; i < arr.size(); i++){
            count[arr[i]]++;
        }
        
        for(int i = 0; i < arr.size(); i++){
            if(count[arr[i]] > 1){
                return i + 1;
            }
        }
        
        return -1;
    }
};