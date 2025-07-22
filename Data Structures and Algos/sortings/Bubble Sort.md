#sorting/bubblesort

- Simplest sorting algo that works by repeatedly swapping the adjacent elements if they are in the wrong order.  
 - Not suitable for large data sets as its average and worst case time complexity is high

![[bubble-sort-1.webp]]![[bubble-sort-2.webp]]![[bubble-sort-3.webp]]

```java
// Optimized java implementation of Bubble sort
import java.io.*;

class GFG {
    
    // An optimized version of Bubble Sort
    static void bubbleSort(int arr[], int n){
        int i, j, temp;
        boolean swapped;
        for (i = 0; i < n - 1; i++) {
            swapped = false;
            for (j = 0; j < n - i - 1; j++) {
                if (arr[j] > arr[j + 1]) {
                    
                    // Swap arr[j] and arr[j+1]
                    temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                    swapped = true;
                }
            }

            // If no two elements were
            // swapped by inner loop, then break
            if (swapped == false)
                break;
        }
    }

    // Function to print an array
    static void printArray(int arr[], int size){
        int i;
        for (i = 0; i < size; i++)
            System.out.print(arr[i] + " ");
        System.out.println();
    }

    // Driver program
    public static void main(String args[]){
        int arr[] = { 64, 34, 25, 12, 22, 11, 90 };
        int n = arr.length;
        bubbleSort(arr, n);
        System.out.println("Sorted array: ");
        printArray(arr, n);
    }
}
```


Time complexity :  O(n^2)
space complexity:  O(1)


**Advantages**
 - easy to understand and implement
 - does not require extra memory
 - stable sorting algo, meaning that element with the same key value maintain their relative order in sorted output.


**Disadvantages**
- Bubble sort has the time complexity O(n^2) makes it very slow for large data sets
- Bubble sort has almost no or limited real world applications