Quick Sort in Java

This project demonstrates the implementation of the Quick Sort algorithm using Java.

About Quick Sort

Quick Sort is an efficient sorting algorithm based on the Divide and Conquer approach.

The algorithm works as follows:

Choose a pivot element.
Rearrange the array so:
Smaller elements go to the left of pivot.
Larger elements go to the right of pivot.
Recursively apply the same process to left and right subarrays.

In this implementation, the last element is chosen as the pivot.

How It Works

For the input:

[2, 7, 1, 8, 3, 5]

After sorting:

[1, 2, 3, 5, 7, 8]
Time Complexity
Case	Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n²)
Space Complexity
Complexity
O(log n)
Java Implementation
```
public class QuickSort {

    public static void main(String[] args) {

        int[] arr = {2, 7, 1, 8, 3, 5};
        int low = 0;
        int high = arr.length - 1;

        quickSort(arr, low, high);

        for(int num : arr) {
            System.out.print(num + " ");
        }
    }

    public static void quickSort(int[] arr, int low, int high) {

        if(low < high) {

            int pi = partition(arr, low, high);

            quickSort(arr, low, pi - 1);
            quickSort(arr, pi + 1, high);
        }
    }

    public static int partition(int[] arr, int low, int high) {

        int pivot = arr[high];
        int i = low - 1;

        for(int j = low; j < high; j++) {

            if(arr[j] < pivot) {

                i++;

                int temp = arr[i];
                arr[i] = arr[j];
                arr[j] = temp;
            }
        }

        int temp = arr[i + 1];
        arr[i + 1] = arr[high];
        arr[high] = temp;

        return i + 1;
    }
}
Output
1 2 3 5 7 8
