# Selection Sort

## Introduction
Selection Sort is a simple comparison-based sorting algorithm.  
It repeatedly selects the smallest element from the unsorted part of the array and places it at the beginning.  

- Algorithm type: Comparison-based  
- Time Complexity:  
  - Best: O(n²)  
  - Average: O(n²)  
  - Worst: O(n²)  
- Space Complexity: O(1) (in-place sorting)  
- Stable: No  

---

## Algorithm Steps
1. Start from the first element.  
2. Find the minimum element in the unsorted part of the array.  
3. Swap it with the first element of the unsorted part.  
4. Move the boundary of the sorted and unsorted parts forward by one.  
5. Repeat until the array is sorted.  

---

## Example Walkthrough
**Input:**  
[64, 25, 12, 22, 11]


**Steps:**  
1. Find minimum → 11, swap with 64 → [11, 25, 12, 22, 64]  
2. Next round: min = 12, swap with 25 → [11, 12, 25, 22, 64]  
3. Next round: min = 22, swap with 25 → [11, 12, 22, 25, 64]  
4. Last round: already sorted.  

**Output:**  
[11, 12, 22, 25, 64]


---

## C++ Implementation
```cpp
#include <iostream>
using namespace std;

void selectionSort(int arr[], int n) {
    for (int i = 0; i < n - 1; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        swap(arr[i], arr[minIndex]);
    }
}

int main() {
    int arr[] = {64, 25, 12, 22, 11};
    int n = sizeof(arr) / sizeof(arr[0]);

    selectionSort(arr, n);

    cout << "Sorted array: ";
    for (int i = 0; i < n; i++)
        cout << arr[i] << " ";
    return 0;
}
