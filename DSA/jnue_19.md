# DSA Assignment – June 19, 2025

This file contains solutions for the third DSA assignment.

---

## 1. Find the Town Judge

- **Platform:** LeetCode  
- **Link:** [Find the Town Judge](https://leetcode.com/problems/find-the-town-judge/)

```cpp
class Solution {
public:
    int findJudge(int n, vector<vector<int>>& trust) {
        if (trust.size() == 0 && n == 1) return 1;
        if (trust.size() == 0 && n > 1) return -1;

        vector<int> trusted(n + 1, 0);
        vector<int> trusts(n + 1, 0);

        for (int i = 0; i < trust.size(); i++) {
            int a = trust[i][1];
            int b = trust[i][0];
            trusted[a]++;
            trusts[b]++;
        }

        for (int i = 0; i < n + 1; i++) {
            if (trusted[i] == n - 1 && trusts[i] == 0) return i;
        }

        return -1;
    }
};
```

---

## 2. Plus One

- **Platform:** LeetCode  
- **Link:** [Plus One](https://leetcode.com/problems/plus-one/description/)

```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& v) {
        int n = v.size();
        for (int i = n - 1; i >= 0; i--) {
            if (i == n - 1)
                v[i]++;
            if (v[i] == 10) {
                v[i] = 0;
                if (i != 0) {
                    v[i - 1]++;
                } else {
                    v.push_back(0);
                    v[i] = 1;
                }
            }
        }
        return v;
    }
};
```

---

## 3. Maximum Subarray

- **Platform:** LeetCode  
- **Link:** [Maximum Subarray](https://leetcode.com/problems/maximum-subarray/description/)

```cpp
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int res = nums[0];
        int total = 0;

        for (int n : nums) {
            if (total < 0) {
                total = 0;
            }
            total += n;
            res = max(res, total);
        }

        return res;
    }
};
```

---

## 4. Assign Cookies

- **Platform:** LeetCode  
- **Link:** [Assign Cookies](https://leetcode.com/problems/assign-cookies/description/)

```cpp
class Solution {
public:
    int findContentChildren(vector<int>& g, vector<int>& s) {
        int cookiesNums = s.size();
        if (cookiesNums == 0) return 0;
        sort(g.begin(), g.end());
        sort(s.begin(), s.end());

        int maxNum = 0;
        int cookieIndex = cookiesNums - 1;
        int childIndex = g.size() - 1;
        while (cookieIndex >= 0 && childIndex >= 0) {
            if (s[cookieIndex] >= g[childIndex]) {
                maxNum++;
                cookieIndex--;
                childIndex--;
            } else {
                childIndex--;
            }
        }
        return maxNum;
    }
};
```