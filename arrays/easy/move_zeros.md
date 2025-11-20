## Move Zeroes

## [https://leetcode.com/problems/move-zeroes/](https://leetcode.com/problems/move-zeroes/)

### Approach

* Maintain pointer `i` for the next position to place a nonzero.
* Iterate with `j`; when `nums[j]` is nonzero and `nums[i]` is zero, swap them.
* Increment `i` whenever the value at `i` becomes nonzero.
* Ensures all nonzero elements shift left while preserving order.

### Complexity (Time & Space)

* Time: O(n)
* Space: O(1)

### Patterns / Techniques

* Two-pointer
* In-place swapping

### Code

```cpp
class Solution {
public:
    void moveZeroes(vector<int>& nums) {
        int n=nums.size();
        int i=0;
        for(int j=1; j<n; j++){
            if(nums[i]!=0){
                i++;
            }
            if(nums[i]==0 && nums[j]!=0){
                swap(nums[i], nums[j]);
                i++;
            }
        }
    }
};
```
