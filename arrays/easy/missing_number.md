## Missing Number — C++

## [https://leetcode.com/problems/missing-number/](https://leetcode.com/problems/missing-number/)

### Approach

* Compute expected sum of numbers from `0` to `n` using formula `n*(n+1)/2`.
* Compute the sum of all elements in the array.
* The missing number is the difference between expected total and actual sum.

### Complexity (Time & Space)

* Time: O(n)
* Space: O(1)

### Patterns / Techniques

* Math formula
* Summation

### Code

```cpp
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size();
        int total=(n*(n+1))/2;
        int arrTotal=0;
        for(int i=0; i<n; i++){
            arrTotal=arrTotal+nums[i];
        }
        return total-arrTotal;
    }
};
```
