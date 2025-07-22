#sorting/quicksort

(understand it again not done from your side)
**QuickSort** is a sorting algorithm based on the Divide and Conquer that picks an element as a pivot and partitions the given array around the picked pivot by placing the pivot in its correct position in the sorted array.

![[quick-sort-1.webp]]
![[quick-sort-2.webp]]
![[Pasted image 20250722111609.png]]
![[quick-sort-4.webp]]
![[Pasted image 20250722111619.png]]![[quick-sort-6.webp]]


```java
import java.util.Arrays;

class GfG {

    // Partition function
    static int partition(int[] arr, int low, int high) {
        
        // Choose the pivot
        int pivot = arr[high];
        
        // Index of smaller element and indicates 
        // the right position of pivot found so far
        int i = low - 1;

        // Traverse arr[low..high] and move all smaller
        // elements to the left side. Elements from low to 
        // i are smaller after every iteration
        for (int j = low; j <= high - 1; j++) {
            if (arr[j] < pivot) {
                i++;
                swap(arr, i, j);
            }
        }
        
        // Move pivot after smaller elements and
        // return its position
        swap(arr, i + 1, high);  
        return i + 1;
    }

    // Swap function
    static void swap(int[] arr, int i, int j) {
        int temp = arr[i];
        arr[i] = arr[j];
        arr[j] = temp;
    }

    // The QuickSort function implementation
    static void quickSort(int[] arr, int low, int high) {
        if (low < high) {
            
            // pi is the partition return index of pivot
            int pi = partition(arr, low, high);

            // Recursion calls for smaller elements
            // and greater or equals elements
            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    public static void main(String[] args) {
        int[] arr = {10, 7, 8, 9, 1, 5};
        int n = arr.length;
      
        quickSort(arr, 0, n - 1);
        
        for (int val : arr) {
            System.out.print(val + " ");  
        }
    }
}
```
Time complexity : O(n^2)
Space complexity : O(n)


## ****Advantages of Quick Sort****

- It is a divide-and-conquer algorithm that makes it easier to solve problems.
- It is efficient on large data sets.
- It has a low overhead, as it only requires a small amount of memory to function.
- It is Cache Friendly as we work on the same array to sort and do not copy data to any auxiliary array.
- Fastest general purpose algorithm for large data when stability is not required.
- It is [****tail recursive****](https://www.geeksforgeeks.org/tail-recursion/) and hence all the [tail call optimization](https://www.geeksforgeeks.org/quicksort-tail-call-optimization-reducing-worst-case-space-log-n/) can be done.


## Disadvantages of Quick Sort

- It has a worst-case time complexity of O(n^2), which occurs when the pivot is chosen poorly.
- It is not a good choice for small data sets.
- It is not a stable sort, meaning that if two elements have the same key, their relative order will not be preserved in the sorted output in case of quick sort, because here we are swapping elements according to the pivot's position (without considering their original positions).

### **Applications of Quick Sort**:

- ✅ **General-purpose sorting** in many standard libraries (e.g., C++, Java)
    
- ✅ Used when **average-case performance is important** (O(n log n))
    
- ✅ Sorting **large datasets** in-place (less memory usage than merge sort)
    
- ✅ **Numerical computing** (e.g., MATLAB, NumPy use variants of quicksort)
    
- ✅ **Databases** for sorting records (e.g., by ID, name, date)
    
- ✅ **File systems** to maintain sorted directory listings
    
- ✅ **Embedded systems** due to its **low overhead**
    
- ✅ Used in **Quickselect** (to find kth smallest/largest elements)