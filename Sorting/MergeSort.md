Merge Sort in Java

This project demonstrates the implementation of Merge Sort using Java.

About Merge Sort

Merge Sort follows the Divide and Conquer approach.

It works by:

Dividing the array into two halves.
Recursively sorting both halves.
Merging the sorted halves into one sorted array.
Example

Input:

[10, 60, 30, 20, 4, 83]

Output:

[4, 10, 20, 30, 60, 83]
Time Complexity
Case	Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n log n)
Space Complexity

O(n)

Correct Java Implementation
import java.util.Arrays;

public class MergeSort {

    public static void main(String[] args) {

        int[] arr = {10, 60, 30, 20, 4, 83};

        sort(arr);

        System.out.println(Arrays.toString(arr));
    }

    public static void sort(int[] arr) {

        if(arr.length == 1) return;

        int[] left = new int[arr.length / 2];
        int[] right = new int[arr.length - left.length];

        for(int i = 0; i < left.length; i++) {
            left[i] = arr[i];
        }

        for(int i = 0; i < right.length; i++) {
            right[i] = arr[i + left.length];
        }

        sort(left);
        sort(right);

        merge(left, right, arr);
    }

    public static void merge(int[] l, int[] r, int[] arr) {

        int i = 0, j = 0, k = 0;

        while(i < l.length && j < r.length) {

            if(l[i] < r[j]) {
                arr[k++] = l[i++];
            }
            else {
                arr[k++] = r[j++];
            }
        }

        while(i < l.length) {
            arr[k++] = l[i++];
        }

        while(j < r.length) {
            arr[k++] = r[j++];
        }
    }
}
Concepts Practiced
Recursion
Divide and Conquer
Array splitting
Merging sorted arrays
Time complexity optimization
