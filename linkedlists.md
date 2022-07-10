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



So what is the Big O Notation?

When using Queue and Dequeue, you are dealing with a Big O of "O(n)"
However, if you decide to work with linked list, you might see a Big O of "O(1)"






## Example 
Lets look at an example of a queue for the resturant:
Note: We solve the problem in line 71-77. See the comments to better understand the purpose. 

```python 

class TakeOrder:

    def __init__(self, order, price, customer):
    """
    We declare the objects that will go into the Queue and the methods will print them out.
    """
        self.order = order
        self.price = price
        self.customer = customer

    def display(self):
        print("{} - {} for {}." 
            .format(self.customer, self.price, self.order))

    def orders(self):
        self.display()
        print("Order(s) for customer(s)")

def main():
"""
The employee will have the option to take more orders or make the orders in the queue
"""
    selection = None
    resturant_queue = []
    while (selection != "3"):
        print()
        print("Items in resturant queue: {}" .format(len(resturant_queue)))
        print("Queue: {}" .format(resturant_queue))
        print("Options:")
        print("1. Add a new order to make")
        print("2. Make next Order")
        print("3. Quit")
        selection = input("Enter selection: ")
        print()
        if selection == "1":
            order = input("Food Order: ")
            price = input("Price: ")
            customer = input("Customer Name: ")
            task = TakeOrder(order, price, customer)
            print(f"appending task {task}")
            #add the objects to the queue with append 
            resturant_queue.append(task)
        elif selection == "2":
        # The orders are made and removed from the queue 
          if len(resturant_queue) > 0:
            item = resturant_queue[0]
            del resturant_queue[0]
            item.orders()
    print("Goodbye")

if __name__ == "__main__":
    main()
  

```

## Task for you to Solve 

Follow the link, Read the comments to see what you will do to design and solve your own queue program.
There is a main file, which you will complete, and an answer file for when youre complete.

https://replit.com/@TylerElms/Queue-tutorial?v=1
