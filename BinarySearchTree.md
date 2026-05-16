Binary Search Tree in Java

This project demonstrates the implementation of a Binary Search Tree using Java.

About Binary Search Tree

A Binary Search Tree (BST) is a tree data structure where:

Left subtree contains values smaller than the root
Right subtree contains values greater than the root

Example:

        50
       /  \
     30    70
    / \    / \
   20 40  60 80
Operations Implemented

✅ Insert node
✅ Search node
✅ Inorder traversal
✅ Preorder traversal
✅ Postorder traversal

Traversals
Inorder (Left → Root → Right)
```
public class BinarySearchTree {

    // Node class
    class Node {

        int data;
        Node left;
        Node right;

        Node(int data) {
            this.data = data;
            left = null;
            right = null;
        }
    }

    Node root;

    // Insert
    public Node insert(Node root, int data) {

        if(root == null) {
            root = new Node(data);
            return root;
        }

        if(data < root.data) {
            root.left = insert(root.left, data);
        }
        else if(data > root.data) {
            root.right = insert(root.right, data);
        }

        return root;
    }

    // Search
    public boolean search(Node root, int key) {

        if(root == null) {
            return false;
        }

        if(root.data == key) {
            return true;
        }

        if(key < root.data) {
            return search(root.left, key);
        }

        return search(root.right, key);
    }

    // Inorder (Left Root Right)
    public void inorder(Node root) {

        if(root != null) {

            inorder(root.left);

            System.out.print(root.data + " ");

            inorder(root.right);
        }
    }

    // Preorder (Root Left Right)
    public void preorder(Node root) {

        if(root != null) {

            System.out.print(root.data + " ");

            preorder(root.left);

            preorder(root.right);
        }
    }

    // Postorder (Left Right Root)
    public void postorder(Node root) {

        if(root != null) {

            postorder(root.left);

            postorder(root.right);

            System.out.print(root.data + " ");
        }
    }

    public static void main(String[] args) {

        BinarySearchTree bst = new BinarySearchTree();

        bst.root = bst.insert(bst.root, 50);
        bst.root = bst.insert(bst.root, 30);
        bst.root = bst.insert(bst.root, 70);
        bst.root = bst.insert(bst.root, 20);
        bst.root = bst.insert(bst.root, 40);
        bst.root = bst.insert(bst.root, 60);
        bst.root = bst.insert(bst.root, 80);

        System.out.println("Inorder Traversal:");
        bst.inorder(bst.root);

        System.out.println();

        System.out.println("Search 40: " + bst.search(bst.root, 40));
    }
}

Output:

20 30 40 50 60 70 80
Preorder (Root → Left → Right)

Output:

50 30 20 40 70 60 80
Postorder (Left → Right → Root)

Output:

20 40 30 60 80 70 50
Search Example

Searching 40

Output:

true
Time Complexity
Operation	Average Case	Worst Case
Insert	O(log n)	O(n)
Search	O(log n)	O(n)
Traversal	O(n)	O(n)
