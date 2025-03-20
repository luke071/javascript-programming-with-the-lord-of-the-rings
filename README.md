# JavaScript Programming with the Lord of the Rings
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

A hobbit can only pack one item of each type into his backpack. Help the hobbit create a unique list of items for the expedition.

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

console.log(arePermutation("ring", "gnir"));
```

