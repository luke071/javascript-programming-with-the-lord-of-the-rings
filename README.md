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

The secret spell has been revealed.
  
Spell:
&nbsp;Three Rings for the Elven-kings under the sky,
&nbsp;Seven for the Dwarf-lords in their halls of stone,
&nbsp;Nine for Mortal Men doomed to die,
&nbsp;One for the Dark Lord on his dark throneIn the Land of Mordor where the Shadows lie.
&nbsp;One Ring to rule them all, One Ring to find them,
&nbsp;One Ring to bring them all and in the darkness bind themIn the Land of Mordor where the Shadows lie.
