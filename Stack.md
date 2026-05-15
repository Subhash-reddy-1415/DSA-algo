# Stack Implementation in Java

This project demonstrates the implementation of a Stack data structure using arrays in Java.

## Features

- Push operation
- Pop operation
- Peek operation
- Check if stack is empty
- Display stack elements

## Stack Principle

Stack follows:

LIFO (Last In First Out)

Example:

10 → 20 → 30

Pop operation removes:

30

## Methods Used

### push(int data)

Adds an element to the top of stack.

### pop()

Removes and returns top element.

### peek()

Returns top element without removing it.

### isEmpty()

Checks whether stack is empty.

### printStack()

Displays all stack elements.

## Time Complexity

| Operation | Complexity |
|-----------|-------------|
| Push      | O(1) |
| Pop       | O(1) |
| Peek      | O(1) |

## Output

Top element: 30  
Popped element: 30  
Current Stack:  
10 20 40 50

```
public class Stack {

    int[] arr = new int[5];
    int size;
    int top;

    // Constructor
    public Stack() {
        size = arr.length;
        top = -1;
    }

    // Push operation
    public void push(int data) {

        if (top < size - 1) {
            arr[++top] = data;
            System.out.println(data + " pushed into stack");
        } else {
            System.out.println("Stack Overflow");
        }
    }

    // Pop operation
    public int pop() {

        if (top > -1) {
            return arr[top--];
        } else {
            System.out.println("Stack Underflow");
            return -1;
        }
    }

    // Peek operation
    public int peek() {

        if (top > -1) {
            return arr[top];
        } else {
            System.out.println("Stack is empty");
            return -1;
        }
    }

    // Check if stack is empty
    public boolean isEmpty() {
        return top == -1;
    }

    // Print stack
    public void printStack() {

        if (top == -1) {
            System.out.println("Stack is empty");
            return;
        }

        for (int i = 0; i <= top; i++) {
            System.out.print(arr[i] + " ");
        }

        System.out.println();
    }

    // Main method
    public static void main(String[] args) {

        Stack stack = new Stack();

        stack.push(10);
        stack.push(20);
        stack.push(30);

        System.out.println("Top element: " + stack.peek());

        System.out.println("Popped element: " + stack.pop());

        stack.push(40);
        stack.push(50);

        System.out.println("Current Stack:");
        stack.printStack();
    }
}
