# LeetCode DSA Problems - June 20

## 1. Rotate Image
- **Platform:** LeetCode  
- **Link:** [https://leetcode.com/problems/rotate-image/](https://leetcode.com/problems/rotate-image/)

### Solution (C++):
```cpp
class Solution {
public:
    void rotate(vector<vector<int>>& matrix) {
        int edgeLength = matrix.size();

        // Reverse vertically
        int top = 0;
        int bottom = edgeLength - 1;
        while (top < bottom) {
            for (int col = 0; col < edgeLength; col++) {
                int temp = matrix[top][col];
                matrix[top][col] = matrix[bottom][col];
                matrix[bottom][col] = temp;
            }
            top++;
            bottom--;
        }

        // Transpose
        for (int row = 0; row < edgeLength; row++) {
            for (int col = row + 1; col < edgeLength; col++) {
                int temp = matrix[row][col];
                matrix[row][col] = matrix[col][row];
                matrix[col][row] = temp;
            }
        }        
    }
};
```

---

## 2. 3 Sum
- **Platform:** LeetCode  
- **Link:** [https://leetcode.com/problems/3sum/description/](https://leetcode.com/problems/3sum/description/)

### Solution (C++):
```cpp
class Solution {
public:
    vector<vector<int>> threeSum(vector<int>& nums) {
        vector<vector<int>> res;
        sort(nums.begin(), nums.end());

        for (int i = 0; i < nums.size(); i++) {
            if (i > 0 && nums[i] == nums[i-1]) {
                continue;
            }
            
            int j = i + 1;
            int k = nums.size() - 1;

            while (j < k) {
                int total = nums[i] + nums[j] + nums[k];

                if (total > 0) {
                    k--;
                } else if (total < 0) {
                    j++;
                } else {
                    res.push_back({nums[i], nums[j], nums[k]});
                    j++;

                    while (nums[j] == nums[j-1] && j < k) {
                        j++;
                    }
                }
            }
        }
        return res;        
    }
};
```

---

## 3. Maximum Consecutive Ones
- **Platform:** LeetCode  
- **Link:** [https://leetcode.com/problems/max-consecutive-ones/](https://leetcode.com/problems/max-consecutive-ones/)

### Solution (C++):
```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int res = 0;
        int count = 0;

        for (int n : nums) {
            if (n == 0) {
                count = 0;
            } else {
                count++;
            }

            if (res < count) {
                res = count;
            }
        }

        return res;        
    }
};
```

---

## 4. Design Twitter
- **Platform:** LeetCode  
- **Link:** [https://leetcode.com/problems/design-twitter/description/](https://leetcode.com/problems/design-twitter/description/)

### (Solution not provided above. Add your implementation here.)

---