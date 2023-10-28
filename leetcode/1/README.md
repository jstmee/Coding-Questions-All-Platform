# [1. Two Sum (Easy)](https://leetcode.com/problems/two-sum)

<p>Given an array of integers <code>nums</code>&nbsp;and an integer <code>target</code>, return <em>indices of the two numbers such that they add up to <code>target</code></em>.</p>




**Similar Questions**:
* [3Sum (Medium)](https://leetcode.com/problems/3sum)
* [4Sum (Medium)](https://leetcode.com/problems/4sum)


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