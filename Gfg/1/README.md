# [Pair with largest sum which is less than K in the array
 (Easy)](https://practice.geeksforgeeks.org/problems/pair-with-largest-sum-which-is-less-than-k-in-the-array/1)


**Similar Questions**:
* [Two Sum](https://leetcode.com/problems/two-sum)[Solution](/leetcode/1/Readme.md)
* [pair with largest sum less than k](https://practice.geeksforgeeks.org/problems/pair-with-largest-sum-which-is-less-than-k-in-the-array/1) [Solution](/Gfg/1/README)
* [count good meals](https://leetcode.com/problems/count-good-meals/description/)[Solution](/leetcode/1711/Readme.md)
* [15.3Sum (Medium)](https://leetcode.com/problems/3sum)
* [18.4Sum (Medium)](https://leetcode.com/problems/4sum)
* [923.4Sum with multiplicity (Medium)](https://leetcode.com/problems/3sum-with-multiplicity/)

## Solution 1.

```cpp
// OJ: https://practice.geeksforgeeks.org/problems/pair-with-largest-sum-which-is-less-than-k-in-the-array/1
// Time: O(NlogN)
// Space: O(1)
pair<int, int> Max_Sum(int nums[], int n, int k) {
        sort(nums, nums+n);
        int i = 0, j = n - 1;
        int ans = -1;
        pair<int,int> ans1={0,0};
        while (i < j) {
            if (nums[i] + nums[j] < k) {
                if(nums[i]+nums[j]>ans){
                    ans=nums[i]+nums[j];
                    ans1={nums[i],nums[j]};
                }
                i++;
            } else {
                j--;
            }
        }
        return ans1;
}
```