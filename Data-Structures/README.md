# Data structures with the Lord of the Rings
## Stack data structure

A stack is a data type that is a collection of elements with two main operations:
- push add an element;
- pop remove the last added element.  
Implement the stack data structure using the Hobbit's backpack as an example.

```js
class Node {
  constructor(item) {
    this.item = item;
    this.next = null;
  }
}

class Stack {
  constructor() {
    this.top = null;
    this.size = 0;
  }

  push(item) {
    let newNode = new Node(item);
    newNode.next = this.top;
    this.top = newNode;
    this.size++;
    console.log(`Added ${item} to backpack.`);
  }

  pop() {
    if (this.top === null) {
      console.log("Backpack is empty.");
    } else {
      let currentTop = this.top;
      this.top = this.top.next;
      this.size--;
      currentTop.item;
      console.log("Remove item from backpack.");
    }
  }

  peek() {
    if (this.top === null) {
      console.log("Backpack is empty.");
    } else {
      console.log(`At the top of the backpack is ${this.top.item}.`);
    }
  }

  display() {
    let current = this.top;
    console.log("Contents of the backpack:");
    while (current !== null) {
      console.log(current.item);
      current = current.next;
    }
  }
}

let hobbitBagpack = new Stack();
hobbitBagpack.push("bread"); //Added bread to backpack.
hobbitBagpack.push("butter"); //Added butter to backpack.
hobbitBagpack.peek(); //At the top of the backpack is butter.
hobbitBagpack.push("apple jam"); //Added apple jam to backpack.
hobbitBagpack.display(); //Contents of the backpack: apple jam, butter, bread
```
## Queue data structure
## Tree data structure
## Graph data structure
## Tree data structure
