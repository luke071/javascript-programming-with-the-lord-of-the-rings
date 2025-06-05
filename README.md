# Programming with JavaScript in the world of the Lord of the Rings
## Secret Spell

During the Second Age of Middle-earth, nineteen great rings were forged. Sauron forged one of his own rings, whishing to subjugate the other rings to himself. While forging it, he sang a spell that was supposed to bring it to life. The spell content was saved to the variable secretSpells.

const secretSpells='ฆ$$ThreeฏRings$$forฏtheฏElven-kings$$underฏtheฏsky,;$$Seven$$forฏtheฏDwarf-lords$$inฏtheirฏhallsฏofฏstone,;$$Nine$$forฏMortalฏMen$$doomedฏtoฏdie,;$$One$$forฏtheฏDarkฏLord$$onฏhisฏdarkฏthroneInฏtheฏLandฏofฏMordorฏwhereฏtheฏShadowsฏlie.;$$One$$Ringฏtoฏruleฏthem$$all,ฏOneฏRingฏtoฏfindฏthem,;$$One$$Ringฏtoฏbringฏthemฏall$$andฏinฏtheฏdarknessฏbindฏthemInฏtheฏLandฏofฏMordorฏwhereฏtheฏShadowsฏlie.'

Solution:

```js 
const unsecretSpells=secretSpells.split('ฏ').join(' ');

for (const unsecretSpell of unsecretSpells.split(';')){
  const [banner, number, owner, rest] = unsecretSpell.split('$$');
  const output = `${banner.startsWith('ฆ') ? 'Spell:\n': ''} ${number} ${owner} ${rest}`;
  console.log(output);
}
```

The function returns:
  
Spell:  
&nbsp;Three Rings for the Elven-kings under the sky,  
&nbsp;Seven for the Dwarf-lords in their halls of stone,  
&nbsp;Nine for Mortal Men doomed to die,  
&nbsp;One for the Dark Lord on his dark throneIn the Land of Mordor where the Shadows lie.  
&nbsp;One Ring to rule them all, One Ring to find them,  
&nbsp;One Ring to bring them all and in the darkness bind themIn the Land of Mordor where the Shadows lie.

## A unique list of items for the expedition

Frodo Baggins can only pack one item of each type into his backpack. Help the hobbit create a unique list of items for the expedition.

Solution:

```js 
let backpackItems= ['map', 'penknife', 'cup','cutlery', 'blanket', 'cup', 'map'];

function uniqueBackpackContent(arr){
    let len = arr.length;
    for(let i = 0; i < len; i++){
        for(let j=i +1 ; j <len; j++) {
            if(arr[i] === arr[j]){
                arr.splice(j,1);
                len--;
                j--
            }
        }  
    }
    console.log(`A unique list of items for the expedition: ${arr}.`);
}

uniqueBackpackContent(backpackItems);
}
```

The function returns:
A unique list of items for the expedition: map,penknife,cup,cutlery,blanket.


## Permutation

Help Hobbit check if two strings are permutation of each other.

```js
function arePermutation(str1, str2) {
  let len1 = str1.length;
  let len2 = str2.length;

  if (len1 !== len2) {
    return false;
  }

  let arr1 = str1.split("");
  let arr2 = str2.split("");

  arr1.sort();
  arr2.sort();

  for (let i = 0; i < len1; i++) {
    if (arr1[i] === arr2[i]) {
      return true;
    } else {
      return false;
    }
  }
}

console.log(arePermutation("ring", "gnir"));//true
```

## Palindrome

Merry Brandybuck collects words that are palindromes. Help him to find them.

```js
function arePalindrome(str1, str2) {
  let len1 = str1.length;
  let len2 = str2.length;

  if (len1 !== len2) {
    return false;
  }

  let arr1 = str1.split("");
  let arr2 = str2.split("").reverse();

  for (let i = 0; i < len1; i++) {
    if (arr1[i] === arr2[i]) {
      return true;
    } else {
      return false;
    }
  }
}

console.log(arePalindrome("deified", "deified"));//true
```

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


