
**Similar Questions**:
* [pair with largest sum less than k](https://practice.geeksforgeeks.org/problems/pair-with-largest-sum-which-is-less-than-k-in-the-array/1) [Solution](..../Gfg/1)
*[count good meals]()
* [15.3Sum (Medium)](https://leetcode.com/problems/3sum)
* [18.4Sum (Medium)](https://leetcode.com/problems/4sum)
* [923.4Sum with multiplicity (Medium)](https://leetcode.com/problems/3sum-with-multiplicity/)

## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/count-good-meals/description/
// Time: O(24*n)
// Space: O(n)
class Solution {
public:
    int countPairs(vector<int>& nums) {
        int mod=1e9+7;
        vector<long long> v;
        int temp=1;
        for(int i=1;i<=24;i++){
            v.push_back(temp);
            temp=temp*2;
        }
        int ans=0;
        int n=nums.size();
        for(int i=0;i<v.size();i++){
            int target=(int)v[i];
            unordered_map<int,int> mp;
            for(int j=0;j<n;j++){
                if(mp.find(target-nums[j])!=mp.end()){
                    ans=(ans%mod+mp[target-nums[j]]%mod)%mod;
                }
                mp[nums[j]]++;
            }
        }
        return ans%mod;

        
    }
};
```

