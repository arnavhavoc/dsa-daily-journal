## Remove Duplicates from Sorted Array

## [https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/](https://leetcode.com/problems/remove-duplicates-from-sorted-array/description/)

### Approach

* Use two-pointer technique: `i` tracks position of last unique element.
* Iterate with `j`; when a new distinct value appears, place it at `i+1`.
* Increment `i` whenever a new unique element is found.
* Return the count of unique elements as `i + 1`.

### Complexity (Time & Space)

* Time: O(n)
* Space: O(1)

### Patterns / Techniques

* Two-pointer
* In-place array manipulation

### Code

```cpp
class Solution {
public:
    int removeDuplicates(vector<int>& nums) {
        int n=nums.size();
        int i=0;
        for(int j=0; j<n; j++){
            if(nums[j]!=nums[i]){
                nums[i+1]=nums[j];
                i++;
            }
        }
        return i+1;
    }
};
```
