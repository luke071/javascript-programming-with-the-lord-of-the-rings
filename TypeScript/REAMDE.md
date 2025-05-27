# Arrays
```ts
interface member {
    name: string,
    race: string
}
let fellowshipMembers: Array<member>;

fellowshipMembers = [{name: 'Frodo', race: 'Hobbit'}];
fellowshipMembers.push({name: 'Mery', race: 'Hobbit'});
fellowshipMembers.shift()
fellowshipMembers.push({name: 'Pippin', race: 'Hobbit'}, {name: 'Aragorn', race: 'Human'}, {name: 'Legolas', race: 'Elf'}, {name: 'Gimli', race: 'Dwarf'}, {name: 'Boromir', race: 'Human'}, {name: 'Gandalf', race: 'Wizard'});
fellowshipMembers.pop()
fellowshipMembers.unshift({name: 'Gandalf', race: 'Wizard'});
fellowshipMembers.unshift({name: 'Frodo', race: 'Hobbit'});
fellowshipMembers.push({name: 'Sam', race: 'Hobbit'});

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