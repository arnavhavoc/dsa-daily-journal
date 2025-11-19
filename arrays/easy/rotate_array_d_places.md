## Rotate Array

## [https://leetcode.com/problems/rotate-array/](https://leetcode.com/problems/rotate-array/)

### Approach

* Compute effective rotation using `k % n` to avoid unnecessary full rotations; e.g., for `n = 7` and `k = 10`, `k % n = 3`, meaning rotating by 10 steps is identical to rotating by 3.
* Reverse the entire array.
* Reverse the first `k` elements to restore their internal order.
* Reverse the remaining `n - k` elements.
* Use an in-place reverse helper to swap elements efficiently.

### Complexity (Time & Space)

* Time: O(n)
* Space: O(1)

### Patterns / Techniques

* Array reversal
* In-place manipulation

### Code

```cpp
class Solution {
public:
    void reverse(vector<int>& arr, int i, int j){
        while(i<j){
            int temp;
            temp=arr[i];
            arr[i]=arr[j];
            arr[j]=temp;
            i++;
            j--;
        }
    }
    void rotate(vector<int>& nums, int k) {
        int n=nums.size();
        k=k%n;
        if(n<2){
            return;
        }
        reverse(nums, 0, n-1);
        reverse(nums, 0, k-1);
        reverse(nums, k, n-1);
        return;
    }
};
```
