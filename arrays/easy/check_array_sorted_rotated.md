## Check if Array is a Valid Rotation of a Sorted Array — C++ (One-Pass)

## https://leetcode.com/problems/check-if-array-is-sorted-and-rotated/

### Approach
- Count how many times the sorted order breaks (`nums[i] > nums[i+1]`).
- For a valid rotated sorted array, this break can happen **at most once**.
- Also check the rotation boundary: if `nums[n-1] > nums[0]`, it adds one more break.
- If total breaks > 1 → not a valid rotation.

### Code
```cpp
class Solution {
public:
    bool check(vector<int>& nums) {
        int n = nums.size();
        int breaks = 0;

        for (int i = 0; i < n - 1; i++) {
            if (nums[i + 1] < nums[i]) {
                breaks++;
            }
        }

        if (nums[n - 1] > nums[0]) {
            breaks++;
        }

        return breaks <= 1;
    }
};
