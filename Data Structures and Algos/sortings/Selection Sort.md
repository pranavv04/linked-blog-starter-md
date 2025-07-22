#sorting/selectionsort 

Selection sort is a comparison-based sorting algo. It sorts an array by repeatedly selecting the smallest (or largest) element from the unsorted portion and swapping it with the first unsorted element. This process continue until entire array is sorted![[Selection-Sort-Algorithm-1.webp]]
![[Selection-Sort-Algorithm-2.webp]]
![[Selection-Sort-Algorithm-3.webp]]
![[Selection-Sort-Algorithm-4.webp]]
![[Selection-Sort-Algorithm-5.webp]]
![[Selection-Sort-Algorithm-6.webp]]


```java
// Java program for implementation of Selection Sort
import java.util.Arrays;

class GfG {

    static void selectionSort(int[] arr){
        int n = arr.length;
        for (int i = 0; i < n - 1; i++) {
          
            // Assume the current position holds
            // the minimum element
            int min_idx = i;

            // Iterate through the unsorted portion
            // to find the actual minimum
            for (int j = i + 1; j < n; j++) {
                if (arr[j] < arr[min_idx]) {
                  
                    // Update min_idx if a smaller element
                    // is found
                    min_idx = j;
                }
            }

            // Move minimum element to its
            // correct position
            int temp = arr[i];
            arr[i] = arr[min_idx];
            arr[min_idx] = temp;           
        }
    }

    static void printArray(int[] arr){
        for (int val : arr) {
            System.out.print(val + " ");
        }
        System.out.println();
    }
  
    public static void main(String[] args){
        int[] arr = { 64, 25, 12, 22, 11 };

        System.out.print("Original array: ");
        printArray(arr);

        selectionSort(arr);

        System.out.print("Sorted array: ");
        printArray(arr);
    }
}
```


Time complexity : O(n^2)
Space complexity : O(1)


**Advantages**
- Easy to understand and implement, making it ideal for teaching basic sorting concepts
- Require only O(1) extra memory space.
- Requires less number of swaps (or memory write) compared to many other standard algos. Only cycle sort beats it in terms of memory writes. Therefore it can be simple algo choice when memory writes are costly.


**Disadvantages**
 - Selection sort has a time complexity O(n^2) makes it slower
 - Does not maintain the relative order of equal elements which means it is not stable.

**Applications of Selection sort**
- Teaching fundamental sorting mechanisms and algo design
- Suitable for small lists where the overhead of more complex algos isn't justified and memory writing is costly as it required less memory compared to other standard sorting algos
- **Heap Sort algo is based on Selection Sort**
