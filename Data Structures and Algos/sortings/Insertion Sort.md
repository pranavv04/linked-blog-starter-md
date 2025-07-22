#sorting/insertionsort 

Insertion sort is a simple sorting algo that works by iteratively inserting each element of an unsorted list into its correct position in a sorted portion of the list. Its like sorting playing card in your hands. You split the cards into 2 groups: the sorted cards and unsorted cards. Then you pick a card from the unsorted group and put in right place in sorted group
![[Insertion-Sort--1.webp]]
![[Insertion-Sort--2.webp]]
![[Insertion-Sort--3.webp]]
![[Insertion-Sort--4.webp]]
![[Insertion-Sort--5.webp]]



```java
// Java program for implementation of Insertion Sort
public class InsertionSort {
    /* Function to sort array using insertion sort */
    void sort(int arr[])
    {
        int n = arr.length;
        for (int i = 1; i < n; ++i) {
            int key = arr[i];
            int j = i - 1;

            /* Move elements of arr[0..i-1], that are
               greater than key, to one position ahead
               of their current position */
            while (j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j = j - 1;
            }
            arr[j + 1] = key;
        }
    }

    /* A utility function to print array of size n */
    static void printArray(int arr[])
    {
        int n = arr.length;
        for (int i = 0; i < n; ++i)
            System.out.print(arr[i] + " ");

        System.out.println();
    }

    // Driver method
    public static void main(String args[])
    {
        int arr[] = { 12, 11, 13, 5, 6 };

        InsertionSort ob = new InsertionSort();
        ob.sort(arr);

        printArray(arr);
    }
}

```
Time complexity : Best case => O(n) Array already sorted
Worst and Avg Case => O(n^2)

Space complexity :O(1)


**Advantages**
- Simple and easy to implement
- Stable sorting algorithm
- Efficient for small lists and nearly sorted lists
- Space-efficient as it is an in-place algorithm
- Adoptive. the number of inversions is directly proportional to number of swaps. Eg, no swapping happens for a sorted array and it takes O(n) times only


**Disadvantage**
- Inefficient for large lists.
- Not as efficient as other sorting algos (e.g. Merge sort, quick sort) for most cases.


**Applications**
- The list is small or nearly sorted.
- Simplicity and stability are important
- Used as a subroutine in **Bucket Sort**
- Can be useful when array is almost sorted 
- Since insertion sort is suitable for small fixed size arrays, it is used in **Hybrid Sorting algos** along with other efficient algorithms like quick sort and merge sort. When the subarray size becomes small, we switch to insertion sort in the recursive algos.

