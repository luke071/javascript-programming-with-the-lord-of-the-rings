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
&nbsp;During the Second Age of Middle-earth, nineteen great rings were forged.  
&nbsp;Sauron forged one of his own rings, whishing to subjugate the other rings to himself.  
&nbsp;While forging it, he sang a spell that was supposed to bring it to life.  
&nbsp;The secret spell has been revealed.  
