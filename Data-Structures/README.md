# Data structures with the Lord of the Rings
## Stack

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
hobbitBagpack.push("Bread");
hobbitBagpack.push("Butter");
hobbitBagpack.peek();
hobbitBagpack.push("Apple jam");
hobbitBagpack.display();
```
