Second Largest Element — C++ (One-Pass Solution)

Goal: Return the second largest distinct element from an array in O(n) time and O(1) space.

Approach:

Track two values while iterating:
largest → current maximum
slargest → second maximum (initialized as -1 in this case)

Update both when a new largest is found.
Update only slargest when the element is smaller than largest but greater than current slargest.

Code:

```cpp
class Solution {
public:
    int getSecondLargest(vector<int> &arr) {
        int n = arr.size();
        int largest = arr[0];
        int slargest = -1;

        for (int i = 1; i < n; i++) {
            if (arr[i] > largest) {
                slargest = largest;
                largest = arr[i];
            } else if (arr[i] < largest && arr[i] > slargest) {
                slargest = arr[i];
            }
        }
        return slargest;
    }
};
```

Notes:
Works even with duplicates (e.g., [5,5,3] → 3).
Returns -1 if no second largest distinct element exists.