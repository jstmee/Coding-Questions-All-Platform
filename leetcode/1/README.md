# [1. Two Sum (Easy)](https://leetcode.com/problems/two-sum)

<p>Given an array of integers <code>nums</code>&nbsp;and an integer <code>target</code>, return <em>indices of the two numbers such that they add up to <code>target</code></em>.</p>




**Similar Questions**:
* [pair with largest sum less than k](https://practice.geeksforgeeks.org/problems/pair-with-largest-sum-which-is-less-than-k-in-the-array/1) [Solution](./Gfg/1)
* [15.3Sum (Medium)](https://leetcode.com/problems/3sum)
* [18.4Sum (Medium)](https://leetcode.com/problems/4sum)
* [923.4Sum with multiplicity (Medium)](https://leetcode.com/problems/3sum-with-multiplicity/)

## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/two-sum/
// Time: O(NlogN)
// Space: O(N)
class Solution {
public:
    vector<int> twoSum(vector<int>& A, int target) {
        nt n=nums.size();
        int i=0,j=n-1;
        sort(nums.begin(),nums.end());
        while(i<j){
            if(nums[i]+nums[j]==target){
                return {i,j};
            }
            else if(nums[i]+nums[j]<target){
                i++;
            }
            else{
                j--;
            }
        }
        return {};
    }
};
```

## Solution 2.

```cpp
// OJ: https://leetcode.com/problems/two-sum/
// Time: O(N)
// Space: O(N)
class Solution {
public:
    vector<int> twoSum(vector<int>& A, int target) {
        int n=nums.size();
        unordered_map<int,int> mp;
        for(int i=0;i<n;i++){
            int rest=target-nums[i];
            if(mp[rest]!=0){
                return {mp[rest]-1,i}; 
            }
            mp[nums[i]]=i+1;

        }
        return {};
    }
};
```