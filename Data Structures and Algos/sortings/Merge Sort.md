#sorting/mergesort 
Merge sort is a popular sorting algo known for its efficiency and stability. It **follows divide and conquer approach**. It works by recursively dividing the input array into two halves, recursively sorting the two halves and finally merging them back together to obtain the sorted array.


![[Merge-Sort-1.webp]]
![[Merge-Sort-2.webp]]
![[Merge-Sort-3.webp]]
![[Merge-Sort-4.webp]]


```java
import java.io.*;

class GfG {

    // Merges two subarrays of arr[].
    // First subarray is arr[l..m]
    // Second subarray is arr[m+1..r]
    static void merge(int arr[], int l, int m, int r){
        
        // Find sizes of two subarrays to be merged
        int n1 = m - l + 1;
        int n2 = r - m;

        // Create temp arrays
        int L[] = new int[n1];
        int R[] = new int[n2];

        // Copy data to temp arrays
        for (int i = 0; i < n1; ++i)
            L[i] = arr[l + i];
        for (int j = 0; j < n2; ++j)
            R[j] = arr[m + 1 + j];

        // Merge the temp arrays

        // Initial indices of first and second subarrays
        int i = 0, j = 0;

        // Initial index of merged subarray array
        int k = l;
        while (i < n1 && j < n2) {
            if (L[i] <= R[j]) {
                arr[k] = L[i];
                i++;
            }
            else {
                arr[k] = R[j];
                j++;
            }
            k++;
        }

        // Copy remaining elements of L[] if any
        while (i < n1) {
            arr[k] = L[i];
            i++;
            k++;
        }

        // Copy remaining elements of R[] if any
        while (j < n2) {
            arr[k] = R[j];
            j++;
            k++;
        }
    }

    // Main function that sorts arr[l..r] using
    // merge()
    static void mergeSort(int arr[], int l, int r){
        
        if (l < r) {

            // Find the middle point
            int m = l + (r - l) / 2;

            // Sort first and second halves
            mergeSort(arr, l, m);
            mergeSort(arr, m + 1, r);

            // Merge the sorted halves
            merge(arr, l, m, r);
        }
    }

    // Driver code
    public static void main(String args[]){
        
        int arr[] = {38, 27, 43, 10};
        
        mergeSort(arr, 0, arr.length - 1);
        
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");
        System.out.println();
    }
}
```

Time complexity : O(`nlogn`)
Space complexity : O(n)


**Applications**
- Sorting large datasets
- External sorting  (when dataset is too large to fit in memory)
- Inversion counting
- Merge sort and its variations are used in library methods or programming lang.
     - Its variation TimSort is used in Python, Java Android and Swift. The main reason why it is preferred to sort non-primitive types is stability which is not there in quick sort
     - **`Arrays.sort` in java uses quicksort while `Collections.sort` uses merge sort**
 - It is a preferred algo for sorting LINKED LISTS
 - It can be easily parallelized as we can independently sort subarrays and then merge
 - The merge function of merge sort to efficiently solve the problems like **union and intersection of two sorted arrays.**

**Advantages**
- Stability : Merge sort is a stable sorting algo, which means it maintains the relative order of equal elements in the input array.
- Guaranteed worst-case performance: Merge sort has a worst-case time complexity O(`N logN`), which means it performs well even on large datasets.
- Simple to implement: The divide and conquer approach is straightforward.
- Naturally Parallel : We independently merge subarrays that makes it suitable for parallel processing.

**Disadvantages**
- Space complexity is high
- Not in place: Merge sort is not an in place sorting algo, which means it required additional memory to store sorted data.
- Merge sort is slower than quick sort in general as quick sort is more cache friendly because it works in place.