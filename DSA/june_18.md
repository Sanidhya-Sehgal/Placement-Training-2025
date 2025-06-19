# DSA Assignment – June 18, 2025

This file contains solutions for the second DSA assignment.

---

## 1. Two Sum

- **Platform:** LeetCode  
- **Link:** [Two Sum](https://leetcode.com/problems/two-sum/)

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        for (int i = 0; i < nums.size(); i++) {
            for (int j = i + 1; j < nums.size(); j++) {
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};
```

---

## 2. Alone in Couple

- **Platform:** GeeksforGeeks  
- **Link:** [Alone in Couple](https://www.geeksforgeeks.org/problems/alone-in-couple5507/0)

```cpp
class Solution {
public:
    int findSingle(vector<int> &arr) {
        int result = 0;
        for (int i = 0; i < arr.size(); i++) {
            result = result ^ arr[i];
        }
        return result;
    }
};
```

---

## 3. Best Time to Buy and Sell Stock

- **Platform:** LeetCode  
- **Link:** [Best Time to Buy and Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/)

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int buyprice = prices[0];
        int profit = 0;
        for (int i = 1; i < prices.size(); i++) {
            if (buyprice > prices[i]) {
                buyprice = prices[i];
            }
            profit = max(profit, prices[i] - buyprice);
        }
        return profit;
    }
};
```

---

## 4. Sort Colors

- **Platform:** LeetCode  
- **Link:** [Sort Colors](https://leetcode.com/problems/sort-colors/)

```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        unordered_map<int, int> count = {{0, 0}, {1, 0}, {2, 0}};
        for (int num : nums) {
            count[num]++;
        }
        int idx = 0;
        for (int color = 0; color < 3; color++) {
            int freq = count[color];
            for (int j = 0; j < freq; j++) {
                nums[idx] = color;
                idx++;
            }
        }        
    }
};
```