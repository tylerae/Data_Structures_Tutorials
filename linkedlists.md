# Linked Lists

## Introduction 

A linked list in Python is a linear data structure, in which the element is not stored at contiguous memory locations.
Each data element is connected to another data element in form of a pointer.
Linked lists consist of the node where each node has a data field and a link to the next node.
The first node is called the head, and it is the starting point of iteration through a list.
The last node has its next reference pointing to none which means it is the end of the list.
Python does not have linked lists in its standard library.

![image](https://user-images.githubusercontent.com/84347788/178126982-82f1d340-752f-474c-bd2d-39a6b8d818b3.png)


Review here for more info:
source - https://pythonguides.com/linked-lists-in-python/#:~:text=1%20A%20linked%20list%20in%20Python%20is%20a,not%20have%20linked%20lists%20in%20its%20standard%20library.

## How do we work with Linked Lists?

#### Lets start with creating a linked list 

Create a new node (we will call it new_node)

Set the "next" of the new node to the current head (new_node.next = self.head)

Set the "prev" of the current head to the new node (self.head.prev = new_node)

Set the head equal to the new node (self.head = new_node)

#### How to iterate through?

Set the prev of the node after current to the node before current (current.next.prev = current.prev)

Set the next of the node before current to the node after current (current.prev.next = current.next)


##So what is the Big O Notation?

At Head: O(1)
At Tail: O(n)
Geting elements: O(n)


## Example 
Lets look at an example of a queue for the resturant:
Note: We solve the problem in line 71-77. See the comments to better understand the purpose. 

```python 


class LinkedList:
    """
    Implement the LinkedList data structure.  The Node class below is an 
    inner class.  An inner class means that its real name is related to 
    the outer class.  To create a Node object, we will need to 
    specify LinkedList.Node
    """

    class Node:
        """
        Each node of the linked list will have data and links to the 
        previous and next node. 
        """

        def __init__(self, data):
            """ 
            Initialize the node to the data provided.  Initially
            the links are unknown so they are set to None.
            """
            self.data = data
            self.next = None
            self.prev = None

    def __init__(self):
        """
        Initialize an empty linked list.
        """
        self.head = None
        self.tail = None

    def insert_head(self, value):
        """
        Insert a new node at the front (i.e. the head) of the
        linked list.
        """
        # Create the new node
        new_node = LinkedList.Node(value)  
        
        # If the list is empty, then point both head and tail
        # to the new node.
        if self.head is None:
            pass
        # If the list is not empty, then only self.head will be
        # affected.
        else:
            pass
            # Connect new node to the previous head
            # Connect the previous head to the new node
            # Update the head to point to the new node

    def remove_head(self):
        """ 
        Remove the first node (i.e. the head) of the linked list.
        """
        # If the list has only one item in it, then set head and tail 
        # to None resulting in an empty list.
        if self.head == self.tail:
            pass
        # If the list has more than one item in it, then only self.head
        # will be affected.
        elif self.head is not None:
            pass
            # Disconnect the second node from the first node
            # Update the head to point to the second node

    def insert_after(self, value, new_value):
        """
        Insert 'new_value' after the first occurance of 'value' in
        the linked list.
        """
        # Search for the node that matches 'value' by starting at the 
        # head of the list.
        curr = self.head
        while curr is not None:
            if curr.data == value:
                # If the location of 'value' is at the end of the list,
                # then we will affect the self.tail.
                if curr == self.tail:
                    new_node = LinkedList.Node(new_value)
                    # Connect the new node to the current tail

                    # Connect the current tail to the new node

                    # Set the tail to the new node

                # For any other location of 'value', need to create a 
                # new node and reconenct the links to insert.
                else:
                    new_node = LinkedList.Node(new_value)
                    # Connect new node to the node containing 'value'
                    
                    # Connect new node to the node after 'value'

                    # Connect node after 'value' to the new node

                    # Connect the node containing 'value' to the new node

                return # We can exit the function after we insert
            curr = curr.next # Go to the next node to search for 'value'

    def __iter__(self):
        """
        Iterate foward through the Linked List
        """
        curr = self.head  # Start at the begining since this is a forward iteration.


    def __str__(self):
        """
        Return a string representation of the linked list.
        """
        output = "linkedlist["
        first = True
        curr = self.head
        while curr is not None:
            if first:
                first = False
            else:
                output += ", "
            output += str(curr.data)
            curr = curr.next
        output += "]"
        return output

    
# Create Empty Linked List
numbers = LinkedList()
print("Empty Linked List: {}\n".format(numbers))

# Insert 6 numbers including a duplicated value
numbers.insert_head(1)
numbers.insert_head(2)
numbers.insert_head(2)
numbers.insert_head(3)
numbers.insert_head(4)
numbers.insert_head(5)
print("Inserting 6 numbers: {}\n".format(numbers))

# Remove the head
numbers.remove_head()
print("Removing the head: {}\n".format(numbers))

# Insert after the value 3 and the value 5
numbers.insert_after(3, 3.5)
numbers.insert_after(1, 6)
print("Inserting numbers after after the value 3 and the value 1: {}\n".format(numbers))

# Use the iterator to display each value
print("Using iterator to display all numbers:")
for x in numbers:
    print(x)
print()

# Use the iterator to calculate the sum of all the numbers
print("Sum of all numbers: {}\n".format(sum(numbers)))
  

```

## Task for you to Solve 

Follow the link, Read the comments to see what you will do to design and solve your own linked list program.
There is a main file, which you will complete, and an answer file for when youre complete.

https://replit.com/@TylerElms/Queue-tutorial?v=1
