# Linked Lists

## Introduction 

A linked list in Python is a linear data structure, in which the element is not stored at contiguous memory locations.
Each data element is connected to another data element in form of a pointer.
Linked lists consist of the node where each node has a data field and a link to the next node.
The first node is called the head, and it is the starting point of iteration through a list.
The last node has its next reference pointing to none which means it is the end of the list.
Python does not have linked lists in its standard library.

![image](https://user-images.githubusercontent.com/84347788/179636679-f96d0ea4-ca99-4035-a125-8eb5f160a812.png)

Review here for more info:
https://pythonguides.com/linked-lists-in-python/#:~:text=1%20A%20linked%20list%20in%20Python%20is%20a,not%20have%20linked%20lists%20in%20its%20standard%20library.


## Lets start with creating a linked list, specifically, adding elements!

Create a new node (we will call it new_node)

Set the "next" of the new node to the current head (new_node.next = self.head)

Set the "prev" of the current head to the new node (self.head.prev = new_node)

Set the head equal to the new node (self.head = new_node)

![image](https://user-images.githubusercontent.com/84347788/178126982-82f1d340-752f-474c-bd2d-39a6b8d818b3.png)

#### Example

``` python
class Node:
   def __init__(self, dataval=None):
      self.dataval = dataval
      self.nextval = None
class SLinkedList:
   def __init__(self):
      self.headval = None
# Function to add element
   def AtEnd(self, newdata):
      NewNode = Node(newdata)
      if self.headval is None:
         self.headval = NewNode
         return
      laste = self.headval
      while(laste.nextval):
         laste = laste.nextval
      laste.nextval=NewNode
 
 """ Comment Begin
      #If you wanted to add to the begining use this function 
      
      def AtBegining(self,newdata):
      NewNode = Node(newdata)
      Update the new nodes next val to existing node
      NewNode.nextval = self.headval
      self.headval = NewNode
      
      #If you wanted to add in between two elements 
   
      def Inbetween(self,middle_node,newdata):
         if middle_node is None:
            print("The mentioned node is absent")
            return
      NewNode = Node(newdata)
      NewNode.nextval = middle_node.nextval
      middle_node.nextval = NewNode

      #Just make sure to call them respectively 
      
Comment End """
    
# Print the linked list
   def listprint(self):
      printval = self.headval
      while printval is not None:
         print (printval.dataval)
         printval = printval.nextval

list = SLinkedList()
list.headval = Node("Mon")
e2 = Node("Tue")
e3 = Node("Wed")

list.headval.nextval = e2
e2.nextval = e3

list.AtEnd("Thu")

list.listprint()

```

## How to iterate through?

Set the prev of the node after current to the node before current (current.next.prev = current.prev)

Set the next of the node before current to the node after current (current.prev.next = current.next)

#### Example

```python 
class Node:
   def __init__(self, data=None):
      self.data = data
      self.next = None

class LinkedList:
   def __init__(self):
      self.head = None

   # this will print our values 
   def listprint(self):
      printvalue = self.head
      while printvalue is not None:
         print (printvalue.data)
         printvalue = printvalue.next

list = LinkedList()
list.head = Node("Mon")
e2 = Node("Tue")
e3 = Node("Wed")

# we add the second value to the head here 
list.head.next = e2

# The 3rd value is just added to the second one, its that easy!
e2.next = e3

list.listprint()

```

## Removing elements in a linked list

To delete a node in a linked list, we will find the previous node of the node to be deleted. We will change the next of the previous node and a function is called to remove a node. 

Set the "prev" of the second node (self.head.next) to nothing (self.head.next.prev = None)

Set the head to be the second node (self.head = self.head.next)

![image](https://user-images.githubusercontent.com/84347788/179636623-6566ead2-e010-4ea6-ac93-839ab8621e73.png)


#### Example 

```python

class Node:
   def __init__(self, data=None):
     #start with our data and the next element
      self.data = data
      self.next = None
     
class SLinkedList:
  def __init__(self):
    self.head = None

    #creating our linked list 
  def begining(self, data_in):
    NewNode = Node(data_in)
    NewNode.next = self.head
    self.head = NewNode

# We will work on removing elements here 
  def RemoveNode(self, Removekey):
    HeadVal = self.head
         
    if (HeadVal is not None):
      if (HeadVal.data == Removekey):
        self.head = HeadVal.next
        HeadVal = None
        return
    while (HeadVal is not None):
      if HeadVal.data == Removekey:
        break
      prev = HeadVal
      HeadVal = HeadVal.next

    if (HeadVal == None):
      return

    prev.next = HeadVal.next
    HeadVal = None

  #this is our print function - Notice how it starts with the head
  def LListprint(self):
    printvalue = self.head
    while (printvalue):
      print(printvalue.data),
      printvalue = printvalue.next

llist = SLinkedList()
llist.begining("Mon")
llist.begining("Tue")
llist.begining("Wed")
llist.begining("Thu")
llist.RemoveNode("Tue")

#call the print function 
llist.LListprint()

```

## So what is the Big O Notation?

* At Head: O(1)
* At Tail: O(n)
* Getting elements: O(n)

## Task for you to Solve 

Follow the link, Read the comments to see what you will do to design and solve your own linked list program. We will just do an element remove example as it tends to be where students get stuck. Please review the attached link in the intro for more examples and problems to practice. 
There is a main file, which you will complete, and an answer file for when youre complete.

https://replit.com/@TylerElms/Linked-Lists-Tutorial?v=1


