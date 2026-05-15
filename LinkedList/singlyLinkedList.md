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
	public class Node {
		int data;
		Node next;
		
		Node(int data) {
			this.data = data;
			this.next = null;
		}
	}
		
		Node head;
	
		
		public void backInsertion(int data) {
			Node newNode = new Node(data);
			
			if(head == null) {
				head = newNode;
				return;
			}
			Node temp = head;
			while(temp.next != null) {
				temp = temp.next;
			}
			temp.next = newNode;
		}
		
		public void frontInsertion(int data) {
			Node newNode = new Node(data);
			
			newNode.next = head;
			head = newNode;
		
	}
	
		public void display() {
			Node temp = head;
			while(temp != null) {
				System.out.print(temp.data + " -> ");
				temp = temp.next;
			}
			System.out.println("null");
		}
		
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
		
		public void delete(int key) {
			if(head == null) {
				return;
			}
			if(head.data == key) {
				head = head.next;
				return;
			}
			Node temp = head;
			while(temp.next != null && temp.next.data != key) {
				temp = temp.next;
			}
			if(temp.next != null) {
				temp.next  = temp.next.next;
			}
		}
		
		public static void main(String[] args) {
			
			LinkedListDemo list = new LinkedListDemo();
			list.backInsertion(10);
			list.backInsertion(20);
			list.backInsertion(30);
			list.backInsertion(40);
			
			System.out.println("origonal list");
			list.display();
			
			list.frontInsertion(5);
			System.out.println("after front insertion");
			list.display();
			
			System.out.println("searching 20"+ list.search(20));
			
			list.delete(20);
			System.out.println("after deleting 20");
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
