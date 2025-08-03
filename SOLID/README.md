## SOLID
### Single Responsibility Principle

According to this principle, each class should have only one responsibility.

```js
class Hero{
    constructor(name, race) {
        this.name = name;
        this.race = race;
    }

    getHeroInfo() {
        return `${this.name} is a ${this.race}.`;
    }
}

class HeroAttack {
    static attackHero(hero) {
        console.log(hero.getHeroInfo());
    }
}

class HeroDefence {
    static defenceHero(hero) {
        console.log(hero.getHeroInfo());
    }
}


let hero = new Hero('Gandalf', 'Wizard');
HeroAttack.attackHero(hero);
HeroDefence.defenceHero(hero);
```
### Open/Closed Principle

Calculate the distance that Gimli the Dwarf will cover depending on the type of terrain he is moving on. He has 1500 movement points in one turn. Then add new terrain type without modifying existing code. 
We use polymorphism and strategy patern to add new terrain type according to the OCP rule.

```js
class DistanceCalculator {
    constructor(strategy) {
        this.strategy = strategy;
    }

    calculate(moveScores) {
        return this.strategy.calculate(moveScores);
    }
}

class RoadTerrain{
    calculate(moveScores){
        return moveScores / 100;
    }
}

class GrassTerrain{
    calculate(moveScores){
        return moveScores / 150;
    }
}

//Add new terrain type
class GritTerrain{
    calculate(moveScores){
        return moveScores / 125;
    }
}

const roadDistance = new DistanceCalculator(new RoadTerrain());
console.log(roadDistance.calculate(1500));//15
const grassDistance = new DistanceCalculator(new GrassTerrain());
console.log(grassDistance.calculate(1500));//10

const gritDistance = new DistanceCalculator(new GritTerrain());
console.log(gritDistance.calculate(1500));//12
```

### Liskov Substitution Principle

According to this principle, background objects should be interchangeable with base class objects without affecting the correctness of the code. The principle will be explained using the example of a flightless bird, the ostrich. In the world of the Lord of the Rings Ostirith is a distinctively built watchtower at the eastern foot of the Ephel Dúath in the Second Age.

```js
class Animal {
  eat() {
    console.log("I can drink");
  }
}

class Bird extends Animal {
  fly() {
    console.log("I can fly");
  }
}

class Ostrich extends Animal {
  run() {
    console.log("I can run");
  }
}

let eagle = new Bird();
eagle.eat();
eagle.fly();

let ostrich = new Ostrich();
ostrich.eat();
ostrich.run();
```

### Interface Segregation Principle

The interface segregation principle states that a class should not implement interfaces it does not use. In Typescript we can use interface structure to verify that a class conforms to a specific interface.

```ts
class Rider {
  ride() {
    console.log("I can ride.");
  }
}

class AxeFighter {
  axeFight() {
    console.log("I fight with a axe.");
  }
}

class SwordFighter {
  swordFight() {
    console.log("I fight with a sword.");
  }
}

class Hobbit implements Rider, SwordFighter {
  ride() {
    //Ride logic
  }

  swordFight(){
    //Fight with a sword logic
  }
}

class Dwarf implements Rider, AxeFighter {
  ride() {
    //Ride logic
  }

  axeFight() {
    //Fight with a axe logic
  }
}

```

### Dependency Segregation Principle

Higher level modules should not depend on lower level modules. Both should depend on the abstraction.

```js
class Gate {
  open() {}
  close() {}
}

class FortressGate extends Gate {
  open() {
    console.log("The gate of the fortress is open");
  }
  close() {
    console.log("The gate of the fortress is close");
  }
}

class Operator {
  constructor(gate) {
    this.gate = gate;
  }

  operate() {
    this.gate.open();
  }
}

const gateDunharrow = new FortressGate();
const gateDunharrowOperator = new Operator(gateDunharrow);
gateDunharrowOperator.operate();
```

