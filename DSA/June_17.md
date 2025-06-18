# DSA Assignment – June 17, 2025

This file contains solutions for the first DSA assignment.

---

## 1. Reverse Digits

- **Platform:** GeeksforGeeks  
- **Link:** [Reverse Digits](https://www.geeksforgeeks.org/problems/reverse-digits/1)

```cpp
class Solution {
public:
    int reverseDigits(int n) {
        int result = 0;
        while (n > 0) {
            result = result * 10 + n % 10;
            n /= 10;
        }
        return result;
    }
};
```

---

## 2. Search Insert Position

- **Platform:** LeetCode  
- **Link:** [Search Insert Position](https://leetcode.com/problems/search-insert-position/)

```cpp
class Solution {
public:
    int searchInsert(vector<int>& nums, int target) {
        int leftptr = 0;
        int rightptr = nums.size() - 1;
        while (leftptr <= rightptr) {
            int mid = (leftptr + rightptr) / 2;
            if (nums[mid] == target) {
                return mid;
            } else if (nums[mid] < target) {
                leftptr = mid + 1;
            } else {
                rightptr = mid - 1;
            }
        }
        return leftptr;
    }
};
```

---

## 3. Single Number

- **Platform:** LeetCode  
- **Link:** [Single Number](https://leetcode.com/problems/single-number/)

```cpp
class Solution {
public:
    int singleNumber(vector<int>& nums) {
        int result = 0;
        for (int i = 0; i < nums.size(); i++) {
            result = result ^ nums[i];
        }
        return result;
    }
};
```

---

## 4. Missing Number

- **Platform:** LeetCode  
- **Link:** [Missing Number](https://leetcode.com/problems/missing-number/description/)

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int sum = 0;
        for (int i = 0; i < nums.size(); i++) {
            sum += nums[i];
        }
        int actual_sum = (nums.size() * (nums.size() + 1)) / 2;
        return actual_sum - sum;
    }
};
```