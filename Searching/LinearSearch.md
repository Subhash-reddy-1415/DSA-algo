Linear Search in Java

This project demonstrates the implementation of the Linear Search algorithm using Java.

About Linear Search

Linear Search is one of the simplest searching algorithms.

It works by:

Starting from the first element.
Comparing each element with the target value.
Returning the index if the element is found.
Returning -1 if the element is not found.
Example

Input array:

[1, 3, 2, 7, 9]

Target:

17

Output:

Element not found
Time Complexity
Case	Complexity
Best Case	O(1)
Average Case	O(n)
Worst Case	O(n)
Space Complexity

O(1)

Java Implementation
public class Main {

    public static void main(String[] args) {

        int[] arr = {1, 3, 2, 7, 9};
        int target = 17;

        int result = linearSearch(arr, target);

        if(result != -1) {
            System.out.println(target + " found at index: " + result);
        } else {
            System.out.println("Element not found");
        }
    }

    private static int linearSearch(int[] arr, int target) {

        for(int i = 0; i < arr.length; i++) {

            if(arr[i] == target) {
                return i;
            }
        }

        return -1;
    }
}
