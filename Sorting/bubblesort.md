# Bubble Sorting in Java

This project demonstrates the implementation of the **Bubble Sort Algorithm** using Java.

## 📌 Description

Bubble Sort is a simple sorting algorithm that repeatedly compares adjacent elements and swaps them if they are in the wrong order.

This program sorts an integer array in ascending order.

## 🚀 Java Code

```java
public class BubbleSorting {

    public static void main(String[] args) {

        int arr[] = {2, 5, 1, 9, 4};
        int size = arr.length - 1;
        int temp = 0;

        for (int j = 0; j < arr.length; j++) {
            for (int i = 0; i < size - j - 1; i++) {
                if (arr[i] > arr[i + 1]) {
                    temp = arr[i];
                    arr[i] = arr[i + 1];
                    arr[i + 1] = temp;
                }
            }
        }

        for (int num : arr) {
            System.out.print(num + " ");
        }
    }
}


▶️ Output
1 2 4 5 9
🛠️ Technologies Used
Java
Bubble Sort Algorithm
📖 How Bubble Sort Works
Compare adjacent elements.
Swap them if they are in the wrong order.
Repeat the process for all elements.
Continue until the array is sorted.
⏱️ Time Complexity
Case	Time Complexity
Best Case	O(n)
Average Case	O(n²)
Worst Case	O(n²)
