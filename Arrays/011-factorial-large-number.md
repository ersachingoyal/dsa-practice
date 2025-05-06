# Factorials of large numbers

**Problem Link:** [GFG- Factorials of large numbers](https://www.geeksforgeeks.org/problems/factorials-of-large-numbers2508/1)

## Solution

```cpp
class Solution {
  public:
    vector<int> factorial(int n) {
        // code here
        vector<int> ans;
        ans.push_back(1);
        int carry = 0;
        
        for(int i = 2; i <= n; i++){
            for(int j = 0; j < ans.size(); j++){
                int x = ans[j] * i + carry;
                ans[j] = x % 10;
                carry = x / 10;
            }
            while(carry){
                ans.push_back(carry % 10);
                carry = carry / 10;
            }
            carry = 0;
        }
        
        reverse(ans.begin(), ans.end());
        return ans;
    }
};