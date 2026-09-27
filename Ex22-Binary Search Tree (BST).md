# Ex22 Searching for a Book ID in a Binary Search Tree (BST)
## DATE: 03-09-2026
## AIM:
To design and implement java program that constructs a Binary Search Tree (BST) using given Book IDs and checks whether a specific Book ID exists in the BST.
## Algorithm
1. Start the program.
2. Define a Node class to represent each node in the BST with attributes data, left, and right.
3. Define a function insert(root, key) to insert a new Book ID into the BST following BST rules:
4. If the BST is empty, create a new node.
5. If the key is smaller than the root’s data, insert it into the left subtree.
6. If the key is larger, insert it into the right subtree.
7. Define a function search(root, key) to check whether a Book ID exists in the BST:
8. If the root is None, return False.
9. If the root’s data matches the key, return True.
10. Otherwise, recursively search in the left or right subtree depending on the value.
11. In the main section:
12. Create an empty BST and insert a list of Book IDs into it.
13. Display the inserted Book IDs.
14. Prompt the user (or define in code) a Book ID to search for.
15. Use the search() function to determine if it exists.
16. Display the result.
17. Stop the program.
 

## Program:
```java
/*
Program to constructs a Binary Search Tree (BST) using given Book IDs 
Developed by: Syed Mohamed Raihan M
RegisterNumber:  212223040167
*/
import java.util.*;

public class BookIDSearch {
    static class Node {
        int data;
        Node left, right;
        Node(int data) {
            this.data = data;
        }
    }

    public static Node insert(Node root, int key) {
        if (root == null) return new Node(key);
        if (key < root.data) root.left = insert(root.left, key);
        else root.right = insert(root.right, key);
        return root;
    }

    public static boolean search(Node root, int key) {
        if (root == null) return false;
        if (root.data == key) return true;
        if (key < root.data) return search(root.left, key);
        else return search(root.right, key);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        Node root = null;
        for (int i = 0; i < n; i++) {
            root = insert(root, sc.nextInt());
        }
        int q = sc.nextInt();
        while (q-- > 0) {
            int key = sc.nextInt();
            System.out.println(search(root, key) ? "Found" : "Not Found");
        }
    }
}
```

## Output:
<img width="426" height="184" alt="image" src="https://github.com/user-attachments/assets/a3c0ff0c-41e3-411f-b0ce-8c2efd4b8864" />



## Result:
The program has been successfully implemented and executed.
It constructs a Binary Search Tree from the given Book IDs and accurately determines whether a queried Book ID exists in the library system.
