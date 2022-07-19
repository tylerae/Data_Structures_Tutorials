# Binary Trees 

## Intoduction 

Tree represents the nodes connected by edges. It is a non-linear data structure. It has the following properties −
* One node is marked as Root node.
* Every node other than the root is associated with one parent node.
* Each node can have an arbiatry number of chid node.

Heres a picture to help you visualize it!
![image](https://user-images.githubusercontent.com/84347788/179647162-2a4c44b1-2232-4140-aef4-e161b5470ff6.png)

## Creating a Root 

We just create a Node class and add assign a value to the node. This becomes tree with only a root node. Of course this is not techinally a tree because we dont have any nodes under it, but we will just start simple. 

#### Example 

``` python
class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data
   def PrintTree(self):
      print(self.data)

root = Node(10)
root.PrintTree()
# ouput is 10. Easy right? :)
```

## Creating the nodes (The full tree)

To insert nodes into a tree we use the same node class created above and add a insert class to it. The insert class compares the value of the node to the parent node and decides to add it as a left node or a right node. Finally the PrintTree class is used to print the tree.

#### Example 

``` python 
class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data

   def insert(self, data):
# Compare the new value with the parent node
      if self.data:
         if data < self.data:
            if self.left is None:
               self.left = Node(data)
            else:
               self.left.insert(data)
            elif data > self.data:
               if self.right is None:
                  self.right = Node(data)
               else:
                  self.right.insert(data)
      else:
         self.data = data

# Print the tree
   def PrintTree(self):
      if self.left:
         self.left.PrintTree()
      print( self.data),
      if self.right:
         self.right.PrintTree()

# Use the insert method to add nodes
root = Node(12)
root.insert(6)
root.insert(14)
root.insert(3)
root.PrintTree()
```

## Methods for Navigating - In-Order Traversal

There are a few methods for traversing through a binary tree. However, we will just go over in-order traversal.  

In this traversal method, the left subtree is visited first, then the root and later the right sub-tree. We should always remember that every node may represent a subtree itself.

In the below python program, we use the Node class to create place holders for the root node as well as the left and right nodes. Then, we create an insert function to add data to the tree. Finally, the In-order traversal logic is implemented by creating an empty list and adding the left node first followed by the root or parent node.

At last the left node is added to complete the In-order traversal. Please note that this process is repeated for each sub-tree until all the nodes are traversed.

![image](https://user-images.githubusercontent.com/84347788/179649464-9fb38a5e-4932-496a-809d-86e525710b5f.png)


#### Example 

``` python 
class Node:
   def __init__(self, data):
      self.left = None
      self.right = None
      self.data = data
# Insert Node
   def insert(self, data):
      if self.data:
         if data < self.data:
            if self.left is None:
               self.left = Node(data)
            else:
               self.left.insert(data)
         else data > self.data:
            if self.right is None:
               self.right = Node(data)
            else:
               self.right.insert(data)
      else:
         self.data = data
# Print the Tree
   def PrintTree(self):
      if self.left:
         self.left.PrintTree()
      print( self.data),
      if self.right:
         self.right.PrintTree()
# Inorder traversal
# Left -> Root -> Right
   def inorderTraversal(self, root):
      res = []
      if root:
         res = self.inorderTraversal(root.left)
         res.append(root.data)
         res = res + self.inorderTraversal(root.right)
      return res
root = Node(27)
root.insert(14)
root.insert(35)
root.insert(10)
root.insert(19)
root.insert(31)
root.insert(42)
print(root.inorderTraversal(root)) 

```

## Problem to Solve 
You know the drill! If you get stick or want to check your answer there is an answer file. Remember, this practice is just meant to start you building binary trees.

https://replit.com/@TylerElms/Binary-Trees-Tutorial?v=1


