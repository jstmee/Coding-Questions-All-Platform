# [1. Two Sum (Easy)](https://leetcode.com/problems/two-sum)

<p>Given an array of integers <code>nums</code>&nbsp;and an integer <code>target</code>, return <em>indices of the two numbers such that they add up to <code>target</code></em>.</p>




**Similar Questions**:
* [3Sum (Medium)](https://leetcode.com/problems/3sum)
* [4Sum (Medium)](https://leetcode.com/problems/4sum)
* [Two Sum II - Input Array Is Sorted (Medium)](https://leetcode.com/problems/two-sum-ii-input-array-is-sorted)
* [Two Sum III - Data structure design (Easy)](https://leetcode.com/problems/two-sum-iii-data-structure-design)
* [Subarray Sum Equals K (Medium)](https://leetcode.com/problems/subarray-sum-equals-k)
* [Two Sum IV - Input is a BST (Easy)](https://leetcode.com/problems/two-sum-iv-input-is-a-bst)
* [Two Sum Less Than K (Easy)](https://leetcode.com/problems/two-sum-less-than-k)
* [Max Number of K-Sum Pairs (Medium)](https://leetcode.com/problems/max-number-of-k-sum-pairs)
* [Count Good Meals (Medium)](https://leetcode.com/problems/count-good-meals)
* [Count Number of Pairs With Absolute Difference K (Easy)](https://leetcode.com/problems/count-number-of-pairs-with-absolute-difference-k)
* [Number of Pairs of Strings With Concatenation Equal to Target (Medium)](https://leetcode.com/problems/number-of-pairs-of-strings-with-concatenation-equal-to-target)
* [Find All K-Distant Indices in an Array (Easy)](https://leetcode.com/problems/find-all-k-distant-indices-in-an-array)
* [First Letter to Appear Twice (Easy)](https://leetcode.com/problems/first-letter-to-appear-twice)
* [Number of Excellent Pairs (Hard)](https://leetcode.com/problems/number-of-excellent-pairs)
* [Number of Arithmetic Triplets (Easy)](https://leetcode.com/problems/number-of-arithmetic-triplets)
* [Node With Highest Edge Score (Medium)](https://leetcode.com/problems/node-with-highest-edge-score)
* [Check Distances Between Same Letters (Easy)](https://leetcode.com/problems/check-distances-between-same-letters)
* [Find Subarrays With Equal Sum (Easy)](https://leetcode.com/problems/find-subarrays-with-equal-sum)
* [Largest Positive Integer That Exists With Its Negative (Easy)](https://leetcode.com/problems/largest-positive-integer-that-exists-with-its-negative)
* [Number of Distinct Averages (Easy)](https://leetcode.com/problems/number-of-distinct-averages)
* [Count Pairs Whose Sum is Less than Target (Easy)](https://leetcode.com/problems/count-pairs-whose-sum-is-less-than-target)

## Solution 1.

```cpp
// OJ: https://leetcode.com/problems/two-sum/
// Author: github.com/lzl124631x
// Time: O(NlogN)
// Space: O(N)
class Solution {
public:
    vector<int> twoSum(vector<int>& A, int target) {
        vector<vector<int>> v; 
        int N = A.size(), L = 0, R = N - 1;
        for (int i = 0; i < N; ++i) v.push_back({ A[i], i });
        sort(begin(v), end(v));
        while (L < R) {
            int sum = v[L][0] + v[R][0];
            if (sum == target) return { v[L][1], v[R][1] };
            if (sum < target) ++L;
            else --R;
        }
        return {};
    }
};
```

## Solution 2.

```cpp
// OJ: https://leetcode.com/problems/two-sum/
// Author: github.com/lzl124631x
// Time: O(N)
// Space: O(N)
class Solution {
public:
    vector<int> twoSum(vector<int>& A, int target) {
        unordered_map<int, int> m;
        for (int i = 0; i < A.size(); ++i) {
            int t = target - A[i];
            if (m.count(t)) return { m[t], i };
            m[A[i]] = i;
        }
        return {};
    }
};
```