# Binary Search Trees (BST) - Complete Guide

## What is a Binary Search Tree?

A Binary Search Tree (BST) is a hierarchical data structure that maintains elements in sorted order. It's a binary tree where each node has at most two children, and it follows a specific ordering property.

### BST Property
For every node in the tree:
- All nodes in the **left subtree** have values **less than** the node's value
- All nodes in the **right subtree** have values **greater than** the node's value
- Both left and right subtrees are also binary search trees

## Visual Structure

```
Basic BST Example:
        8
       / \
      3   10
     / \    \
    1   6    14
       / \   /
      4   7 13
```

In this tree:
- Root node: 8
- Left subtree of 8: {1, 3, 4, 6, 7} (all < 8)
- Right subtree of 8: {10, 13, 14} (all > 8)

## Core Operations

### 1. Search Operation

**Algorithm:**
```
SEARCH(root, key):
    if root is NULL or root.data == key:
        return root
    
    if key < root.data:
        return SEARCH(root.left, key)
    else:
        return SEARCH(root.right, key)
```

**Time Complexity:** O(h) where h is the height of the tree
- Best case: O(log n) for balanced tree
- Worst case: O(n) for skewed tree

### 2. Insertion Operation

**Algorithm:**
```
INSERT(root, key):
    if root is NULL:
        return new Node(key)
    
    if key < root.data:
        root.left = INSERT(root.left, key)
    else if key > root.data:
        root.right = INSERT(root.right, key)
    
    return root
```

**Visual Example - Inserting 5:**
```
Before:          After:
    8               8
   / \             / \
  3   10          3   10
 / \    \        / \    \
1   6    14     1   6    14
   / \             / \   /
  4   7           4   7 13
                   \
                    5
```

### 3. Deletion Operation

Deletion is the most complex operation with three cases:

**Case 1: Node has no children (leaf node)**
- Simply delete the node

**Case 2: Node has one child**
- Replace the node with its child

**Case 3: Node has two children**
- Find the inorder successor (smallest node in right subtree)
- Replace the node's value with successor's value
- Delete the successor

**Algorithm:**
```
DELETE(root, key):
    if root is NULL:
        return root
    
    if key < root.data:
        root.left = DELETE(root.left, key)
    else if key > root.data:
        root.right = DELETE(root.right, key)
    else:
        // Node to be deleted found
        if root.left is NULL:
            return root.right
        else if root.right is NULL:
            return root.left
        
        // Node has two children
        successor = findMin(root.right)
        root.data = successor.data
        root.right = DELETE(root.right, successor.data)
    
    return root
```

## Tree Traversals

### 1. Inorder Traversal (Left-Root-Right)
```
INORDER(root):
    if root is not NULL:
        INORDER(root.left)
        print(root.data)
        INORDER(root.right)
```
**Result for example tree:** 1, 3, 4, 6, 7, 8, 10, 13, 14
**Note:** Inorder traversal of BST gives sorted sequence!

### 2. Preorder Traversal (Root-Left-Right)
```
PREORDER(root):
    if root is not NULL:
        print(root.data)
        PREORDER(root.left)
        PREORDER(root.right)
```
**Result:** 8, 3, 1, 6, 4, 7, 10, 14, 13

### 3. Postorder Traversal (Left-Right-Root)
```
POSTORDER(root):
    if root is not NULL:
        POSTORDER(root.left)
        POSTORDER(root.right)
        print(root.data)
```
**Result:** 1, 4, 7, 6, 3, 13, 14, 10, 8

## Implementation in Python

```python
class TreeNode:
    def __init__(self, val=0):
        self.val = val
        self.left = None
        self.right = None

class BST:
    def __init__(self):
        self.root = None
    
    def insert(self, val):
        self.root = self._insert_recursive(self.root, val)
    
    def _insert_recursive(self, node, val):
        if not node:
            return TreeNode(val)
        
        if val < node.val:
            node.left = self._insert_recursive(node.left, val)
        elif val > node.val:
            node.right = self._insert_recursive(node.right, val)
        
        return node
    
    def search(self, val):
        return self._search_recursive(self.root, val)
    
    def _search_recursive(self, node, val):
        if not node or node.val == val:
            return node
        
        if val < node.val:
            return self._search_recursive(node.left, val)
        return self._search_recursive(node.right, val)
    
    def delete(self, val):
        self.root = self._delete_recursive(self.root, val)
    
    def _delete_recursive(self, node, val):
        if not node:
            return node
        
        if val < node.val:
            node.left = self._delete_recursive(node.left, val)
        elif val > node.val:
            node.right = self._delete_recursive(node.right, val)
        else:
            # Node to delete found
            if not node.left:
                return node.right
            elif not node.right:
                return node.left
            
            # Node has two children
            successor = self._find_min(node.right)
            node.val = successor.val
            node.right = self._delete_recursive(node.right, successor.val)
        
        return node
    
    def _find_min(self, node):
        while node.left:
            node = node.left
        return node
    
    def inorder(self):
        result = []
        self._inorder_recursive(self.root, result)
        return result
    
    def _inorder_recursive(self, node, result):
        if node:
            self._inorder_recursive(node.left, result)
            result.append(node.val)
            self._inorder_recursive(node.right, result)
```

## Time Complexity Analysis

| Operation | Best Case | Average Case | Worst Case |
|-----------|-----------|--------------|------------|
| Search    | O(log n)  | O(log n)     | O(n)       |
| Insert    | O(log n)  | O(log n)     | O(n)       |
| Delete    | O(log n)  | O(log n)     | O(n)       |

**Space Complexity:** O(n) for storing n nodes

## Balanced vs Unbalanced BST

### Balanced BST
```
Balanced (Height ≈ log n):
      8
     / \
    4   12
   / \ / \
  2  6 10 14
```

### Unbalanced BST (Worst Case)
```
Skewed (Height = n):
1
 \
  2
   \
    3
     \
      4
       \
        5
```

## Applications

1. **Database Indexing**: B-trees (variants of BST) for efficient data retrieval
2. **File Systems**: Directory structures
3. **Expression Parsing**: Syntax trees in compilers
4. **Autocomplete**: Trie structures (specialized BST)
5. **Game Development**: Spatial partitioning, collision detection
6. **Priority Queues**: Heap implementations

## Advantages and Disadvantages

### Advantages
- **Efficient Search**: O(log n) average case
- **Sorted Order**: Inorder traversal gives sorted sequence
- **Dynamic Size**: Can grow and shrink during runtime
- **No Memory Waste**: Only allocates memory as needed

### Disadvantages
- **Worst-case Performance**: O(n) for skewed trees
- **No Random Access**: Unlike arrays, can't access elements by index
- **Additional Memory**: Requires extra memory for pointers
- **Not Cache-friendly**: Nodes may not be stored contiguously

## Variations

1. **AVL Trees**: Self-balancing BST with height difference ≤ 1
2. **Red-Black Trees**: Self-balancing with color properties
3. **Splay Trees**: Self-adjusting BST that moves frequently accessed nodes to root
4. **B-Trees**: Multi-way search trees for databases
5. **Treaps**: Combination of BST and heap properties

## Common Interview Problems

1. **Validate BST**: Check if a binary tree is a valid BST
2. **Lowest Common Ancestor**: Find LCA of two nodes in BST
3. **Convert Sorted Array to BST**: Build balanced BST from sorted array
4. **Kth Smallest Element**: Find kth smallest element in BST
5. **Range Sum Query**: Sum of all nodes in a given range

## Best Practices

1. **Use Self-balancing Trees**: For guaranteed O(log n) performance
2. **Consider Memory Usage**: BST uses more memory than arrays
3. **Handle Duplicates**: Decide whether to allow duplicates and how to handle them
4. **Iterative vs Recursive**: Consider stack overflow for deep trees
5. **Error Handling**: Check for null pointers and edge cases

Binary Search Trees provide an excellent foundation for understanding more complex tree data structures and are essential for many algorithmic problems and real-world applications.
