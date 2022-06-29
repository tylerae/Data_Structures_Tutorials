# Queue 

## Review Stack 

As you already know, a stack is a type of data structure where the elements are catergolrized as "Last in, First Out." Opposite to this, is a queue. It is a data structure catagorized as "first in first out." 

## What is a Queue exactly?

Lets think of a resturant. You make an order and it goes into an order queue. Other people have made orders before you and there are some people who made orders after. 
Luckily, the queue ensures that your food is made in the order it came in. After all, there is nothing more fustrating than seeing people who ordered after you get their food first. 

Lets review some syntax. These are the buiding blocks for a queue 

my_queue.append(value) - Add and element to your queue 
value = my_queue[0] // del my_queue[0] - Use these to lines of code to delete an item from the queue. (I.E. Dequeue)
length = len(my_queue) - check the length of a queue 
if len(my_queue) == 0: - check if queue is zero 

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

https://replit.com/@TylerElms/Queue-tutorial?v=1
