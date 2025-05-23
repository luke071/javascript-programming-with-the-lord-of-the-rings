# Arrays
```ts
let fellowshipMember: string[];

fellowshipMember = ['Frodo'];
fellowshipMember;
fellowshipMember.push('Merry');
fellowshipMember.shift()
fellowshipMember.push('Pippin', 'Aragorn', 'Legolas', 'Gimli', 'Boromir', "Gandalf");
fellowshipMember.pop()
fellowshipMember.unshift('Gandalf');
fellowshipMember.unshift('Frodo');
fellowshipMember.push("Sam");

console.log(`The Fellowship has ` + fellowshipMember.length + ' members. It consists of ' +fellowshipMember+".");
```