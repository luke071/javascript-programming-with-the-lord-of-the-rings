# Arrays
```ts
interface member {
    name: string,
    race: string,
    age: number
}
let fellowshipMembers: Array<member>;

fellowshipMembers = [{name: 'Frodo', race: 'Hobbit', age: 50}];
fellowshipMembers.push({name: 'Mery', race: 'Hobbit', age : 35});
fellowshipMembers.shift()
fellowshipMembers.push({name: 'Pippin', race: 'Hobbit', age : 34}, {name: 'Aragorn', race: 'Human', age: 87}, {name: 'Legolas', race: 'Elf', age: 105}, {name: 'Gimli', race: 'Dwarf', age: 110}, {name: 'Boromir', race: 'Human', age: 40}, {name: 'Gandalf', race: 'Wizard', age:2000});
fellowshipMembers.pop()
fellowshipMembers.unshift({name: 'Gandalf', race: 'Wizard', age: 2000});
fellowshipMembers.unshift({name: 'Frodo', race: 'Hobbit', age: 50});
fellowshipMembers.push({name: 'Sam', race: 'Hobbit', age : 38});

console.log(`The Fellowship has ` + fellowshipMembers.length + " members.");//'The Fellowship has 9 members.'
```
## Array map()
Extracting character names  
```ts
const names = fellowshipMembers.map(member => member.name);
console.log(names);//['Frodo', 'Gandalf', 'Mery', 'Pippin', 'Aragorn', 'Legolas', 'Gimli','Boromir', 'Sam']
```
Creating full character descriptions
```ts
const descriptions = fellowshipMembers.map(member => `${member.name} is a ${member.race}`);
console.log(descriptions[0]);//['Frodo is a Hobbit']
```
Extracting unique races
```ts
const uniqueRaces = [...new Set(fellowshipMembers.map(member => member.race))];
console.log(uniqueRaces);//[ 'Hobbit', 'Wizard', 'Human', 'Elf', 'Dwarf' ]
```
## Array reduce()
Counting the total number of members of the Fellowship of the Ring
```ts
const totalMembers = fellowshipMembers.reduce((member) => member + 1, 0);
console.log(totalMembers);//9
```
Finding the maximum value of a members.
```ts
const maxAge = fellowshipMembers.reduce((acc, curr) => {return Math.max(acc, curr.age);}, 0)
console.log(maxAge)//2000
```
## Array filter()
Filtering by race
```ts
const wizards = fellowshipMembers.filter(member => member.race === "Wizard");
console.log(wizards);//[ { name: 'Gandalf', race: 'Wizard' } ]
```
## Array findIndex()
Finding the member index
```ts
const indexOfAragorn = fellowshipMembers.findIndex(member => member.name === "Aragorn");
console.log(indexOfAragorn);//4
```

