# Design patterns with the Lord of the Rings
## Observer pattern

The observer pattern allows you to define a subscription mechanism to notify objects about events happening in the observed object.
Let's imagine that we have a system of observers in the Inn the Prancing Ponny

```js 
function HobbitObserver(name) {
  this.name = name;
}

HobbitObserver.prototype = {
  update: function (event) {
    console.log(`${this.name} reacts to ${event}`);
  },
};

function Inn() {
  this.observers = [];
}

Inn.prototype = {
  addObserver: function (observer) {
    this.observers.push(observer);
  },

  removeObserver: function (observerToRemove) {
    this.observers = this.observers.filter(
      (observerr) => observerr !== observerToRemove
    );
  },
  notifyObservers: function (event) {
    this.observers.forEach((observer) => observer.update(event));
  },
  notifyObserver: function (event, hobbit) {
    const user = this.observers.find((observer) => observer.name === hobbit);
    user.update(event);
  },
};

const thePrancingPonny = new Inn();
const hobbit1 = new HobbitObserver("Frodo Baggins");
const hobbit2 = new HobbitObserver("Sam");
const hobbit3 = new HobbitObserver("Pippin");
const hobbit4 = new HobbitObserver("Merry");

thePrancingPonny.addObserver(hobbit1);
thePrancingPonny.addObserver(hobbit2);
thePrancingPonny.addObserver(hobbit3);
thePrancingPonny.addObserver(hobbit4);
thePrancingPonny.notifyObservers("We accept orders!");
thePrancingPonny.notifyObserver("Butter rolls with jam for collection!", "Sam");
```

The function returns:

&nbsp;Frodo Baggins reacts to We accept orders!  
&nbsp;Sam reacts to We accept orders!  
&nbsp;Pippin reacts to We accept orders!  
&nbsp;Merry reacts to We accept orders!  
&nbsp;Sam reacts to Butter rolls with jam for collection!
## Mediator pattern
## Strategy pattern


