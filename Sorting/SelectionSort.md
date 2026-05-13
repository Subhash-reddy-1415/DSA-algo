Selection Sort in Java

This project demonstrates the implementation of the Selection Sort algorithm using Java.

About Selection Sort

Selection Sort is a simple sorting algorithm that works by:

Finding the smallest element in the unsorted part of the array.
Swapping it with the first unsorted element.
Repeating the process until the array is sorted.
Time Complexity
Case	Complexity
Best Case	O(n²)
Average Case	O(n²)
Worst Case	O(n²)
Space Complexity

O(1)

Java Code
```
public class SelectionSort {

    public static void main(String[] args) {

        int arr[] = {64, 25, 12, 22, 11};
        int temp = 0;

        for(int j = 0; j < arr.length; j++) {

            int min = j;

            for(int i = j + 1; i < arr.length; i++) {

                if(arr[i] < arr[min]) {
                    min = i;
                }
            }

            temp = arr[min];
            arr[min] = arr[j];
            arr[j] = temp;
        }

        for(int num : arr) {
            System.out.print(num + " ");
        }
    }
}
```
Output
11 12 22 25 64
