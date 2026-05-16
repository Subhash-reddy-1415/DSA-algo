Queue Implementation in Java

This project demonstrates the implementation of a Queue using Java.

About Queue

Queue follows the FIFO (First In First Out) principle.

Example:

10 → 20 → 30 → 40

If we remove an element:

10 removed first
Operations Implemented

✅ Enqueue (Insert)
✅ Dequeue (Remove)
✅ Peek (Front element)
✅ Display Queue

Time Complexity
Operation	Complexity
Enqueue	O(1)
Dequeue	O(1)
Peek	O(1)
```
public class Queue {

    int rear = -1;
    int front = 0;
    int size = 0;

    int[] arr = new int[4];

    public void enqueue(int data) {

        if(rear < arr.length - 1) {

            rear++;
            arr[rear] = data;
            size++;

        } else {
            System.out.println("Queue Overflow");
        }
    }

    public int dequeue() {

        if(size == 0) {

            System.out.println("Queue Underflow");
            return -1;
        }

        int data = arr[front];

        front++;
        size--;

        return data;
    }

    public int peek() {

        if(size == 0) {
            return -1;
        }

        return arr[front];
    }

    public void show() {

        for(int i = front; i <= rear; i++) {
            System.out.print(arr[i] + " ");
        }
    }

    public static void main(String[] args) {

        Queue queue = new Queue();

        queue.enqueue(10);
        queue.enqueue(20);
        queue.enqueue(30);
        queue.enqueue(40);

        System.out.println("Removed: " + queue.dequeue());

        System.out.println("Front: " + queue.peek());

        queue.show();
    }
}
