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

A tree is a data structure made up of elements called nodes. Each node represents a member of the Hobbit family.

```js
class FamilyTreeNode {
  constructor(person) {
    this.person = person;
    this.children = [];
  }

  addChild(child) {
    this.children.push(child);
  }

  display(indent = 0) {
    console.log(" ".repeat(indent) + this.person);
    for (const child of this.children) {
      child.display(indent + 2);
    }
  }
}

class Tree {
  constructor(rootPerson) {
    this.root = new FamilyTreeNode(rootPerson);
  }
  display() {
    if (this.root) {
      this.root.display();
    }
  }
}

let hobbitFamilyTree = new Tree("Hobbit Family Tree");

let line01 = new FamilyTreeNode("Balbo Baggins");
let line11 = new FamilyTreeNode("Mungo Baggins");
let line12 = new FamilyTreeNode("Largo Baggins");
let line21 = new FamilyTreeNode("Bungo Baggins");
let line22 = new FamilyTreeNode("Frosco Baggins");
let line31 = new FamilyTreeNode("Bilbo Baggins");
let line32 = new FamilyTreeNode("Drogo Baggins");
let line41 = new FamilyTreeNode("Frodo Baggins");

hobbitFamilyTree.root.addChild(line01);
line01.addChild(line11);
line01.addChild(line12);
line11.addChild(line21);
line12.addChild(line22);
line21.addChild(line31);
line22.addChild(line32);
line32.addChild(line41);

hobbitFamilyTree.display();
```
## Graph data structure
## Tree data structure
