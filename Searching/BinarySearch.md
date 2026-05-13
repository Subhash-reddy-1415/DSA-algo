Binary Search in Java

This project demonstrates the implementation of the Binary Search algorithm using Java.

About Binary Search

Binary Search is an efficient searching algorithm that works only on sorted arrays.

It works by:

Finding the middle element.
Comparing the target with the middle element.
If target is smaller, search left half.
If target is larger, search right half.
Repeat until the element is found or search space becomes empty.
Example

Input array:

[1, 2, 3, 4, 5, 6, 7, 8]

Target:

7

Output:

Element found at index: 6
Time Complexity
Case	Complexity
Best Case	O(1)
Average Case	O(log n)
Worst Case	O(log n)
Space Complexity

O(1)

Java Implementation
public class Main1 {

    public static void main(String[] args) {

        int[] arr = {1,2,3,4,5,6,7,8};
        int target = 7;

        int right = arr.length - 1;

        int result = binarySearch(arr, target, 0, right);

        if(result != -1) {
            System.out.println("Element found at index: " + result);
        } else {
            System.out.println("Element not found");
        }
    }

    private static int binarySearch(int[] arr, int target, int left, int right) {

        while(left <= right) {

            int mid = (left + right) / 2;

            if(target == arr[mid]) {
                return mid;
            }
            else if(target < arr[mid]) {
                right = mid - 1;
            }
            else {
                left = mid + 1;
            }
        }

        return -1;
    }
}
