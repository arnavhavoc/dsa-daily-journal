## Max Consecutive Ones — C++

## [https://leetcode.com/problems/max-consecutive-ones/submissions/1835095876/](https://leetcode.com/problems/max-consecutive-ones/submissions/1835095876/)

### Approach

* Track current streak of consecutive `1`s using `currMax`.
* Increase `currMax` when encountering `1`, else reset to `0`.
* Update global maximum `maxi` whenever `currMax` increases.
* Return the highest streak found.

### Complexity (Time & Space)

* Time: O(n)
* Space: O(1)

### Patterns / Techniques

* Linear scan
* Counting streaks

### Code

```cpp
class Solution {
public:
    int findMaxConsecutiveOnes(vector<int>& nums) {
        int n=nums.size();
        int maxi=0;
        int currMax=0;
        for(int i=0; i<n; i++){
            if(nums[i]==1){
                currMax++;
                maxi=max(maxi, currMax);
            }
            else{
                currMax=0;
            }
        }
        return maxi;
    }
};
```
