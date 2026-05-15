Singly Linked List in Java

This project demonstrates the implementation of a Singly Linked List using Java.

About Linked List

A Linked List is a linear data structure where each element (node) contains:

Data → stores the value
Next → stores the reference to the next node

Unlike arrays, linked lists do not store elements in contiguous memory.

Features Implemented

This project includes:

✅ Insert at end
✅ Insert at beginning
✅ Display list
✅ Search element
✅ Delete element
```
public class LinkedListDemo {

    // Node class
    static class Node {

        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    // Head pointer
    Node head;

    // Insert at end
    public void insert(int data) {

        Node newNode = new Node(data);

        // If list is empty
        if(head == null) {
            head = newNode;
            return;
        }

        // Traverse to last node
        Node temp = head;

        while(temp.next != null) {
            temp = temp.next;
        }

        // Connect last node to new node
        temp.next = newNode;
    }

    // Insert at beginning
    public void insertAtBeginning(int data) {

        Node newNode = new Node(data);

        // New node points to current head
        newNode.next = head;

        // Move head to new node
        head = newNode;
    }

    // Display linked list
    public void display() {

        Node temp = head;

        while(temp != null) {
            System.out.print(temp.data + " -> ");
            temp = temp.next;
        }

        System.out.println("null");
    }

    // Search an element
    public boolean search(int key) {

        Node temp = head;

        while(temp != null) {

            if(temp.data == key) {
                return true;
            }

            temp = temp.next;
        }

        return false;
    }

    // Delete a node by value
    public void delete(int key) {

        // Empty list
        if(head == null) {
            return;
        }

        // If first node needs deletion
        if(head.data == key) {
            head = head.next;
            return;
        }

        Node temp = head;

        // Find previous node
        while(temp.next != null && temp.next.data != key) {
            temp = temp.next;
        }

        // Delete node
        if(temp.next != null) {
            temp.next = temp.next.next;
        }
    }

    public static void main(String[] args) {

        LinkedListDemo list = new LinkedListDemo();

        // Insert at end
        list.insert(10);
        list.insert(20);
        list.insert(30);

        System.out.println("Original List:");
        list.display();

        // Insert at beginning
        list.insertAtBeginning(5);

        System.out.println("After inserting at beginning:");
        list.display();

        // Search
        System.out.println("Searching 20: " + list.search(20));

        // Delete
        list.delete(20);

        System.out.println("After deleting 20:");
        list.display();
    }
}

Example Output
Original List:
10 -> 20 -> 30 -> null

After inserting at beginning:
5 -> 10 -> 20 -> 30 -> null

Searching 20: true

After deleting 20:
5 -> 10 -> 30 -> null
Time Complexity
Operation	Complexity
Insert at Beginning	O(1)
Insert at End	O(n)
Search	O(n)
Delete	O(n)
Display	O(n)
