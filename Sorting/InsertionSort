Insertion Sort in Java

This project demonstrates the implementation of the Insertion Sort algorithm using Java.

About Insertion Sort

Insertion Sort works similarly to how people arrange playing cards in their hands.

The algorithm:

Starts from the second element.
Compares it with previous elements.
Shifts larger elements one position to the right.
Inserts the current element into its correct position.
Time Complexity
Case	Complexity
Best Case	O(n)
Average Case	O(n²)
Worst Case	O(n²)
Space Complexity

O(1)

Java Implementation
```
public class InsertionSort {

    public static void main(String[] args) {

        int arr[] = {10, 7, 3, 1, 43, 12};

        for(int i = 1; i < arr.length; i++) {

            int key = arr[i];
            int j = i - 1;

            while(j >= 0 && arr[j] > key) {
                arr[j + 1] = arr[j];
                j--;
            }

            arr[j + 1] = key;
        }

        for(int nums : arr) {
            System.out.print(nums + " ");
        }
    }
}
```
Output
1 3 7 10 12 43
