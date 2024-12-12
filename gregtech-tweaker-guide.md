The Ultimate Guide to MTUtilsGT - the most confusing yet most useful mod ever
I am Andrew, and I had a really big need of adding a recipe to a GregTech 6 Centrifuge. But, I struggled with this mod. Hell, I had to download TerraFirmaRescue to discover how this mod works! However, now YOU dont have to struggle as I had to! This is because, THIS page exists!
First, we want to identify the machine. For this, we use:
```Minecraft_Command
/mtu GTkey ""
```
where we place the machine name inside "", for example "Centrifuge", thus we get:
```Minecraft_Command
/mtu GTkey "Centrifuge"
```
You will get the wanted result.
Now, here is a catch: imports dont exist in MineTweaker 3, so we MUST use a legacy alternative: write mods. everywhere.
Now, we want to identify the item and fluids we need. For items, we can use:
```Minecraft_Command
/mt hand
```
, while what we can use for fluids is pressing F3+H to turn on advanced descriptions (if you didnt already) and hover our cursor on the fluid in NEI and see their Registry. What we use in MineTweaker 3 for this is just go ahead, and type liquid: before the Registry value.
"What now?" you may ask. Well, now its time for the FUN part! Making the goddamn code itself!
Now, here is a template, that will give us an example:
```ZenScript
mods.MTUtilsGT.addCustomRecipe("gt.recipe.centrifuge", false, 16, 10, 0, [10000], 
[<TConstruct:slime.gel:1>], [],
[<liquid:glue>*1000, <liquid:latex>*288],  []);
```
What this does is it uses a Centrifuge ("gt.recipe.centrifuge"), does NOT hide the recipe in NEI (bool false, but you CAN hide it with bool true), specify how much GU/t you supply (in this case 16) and the time for the recipe in ticks (10 in this case).
We then add "[10000]" which I... do not understand why, but do NOT remove it, it WILL break the code. Same for the "0" before "[10000]". Now, we get to the fun part. First, we have "[<TConstruct:slime.gel:1>]" - here we have the item input, and you can add a star and number after the > to specify how many of those items are required.
Then, there is a [] (aka [null]) value, which is for fluid input. In this recipe there is no fluid input, but you CAN add fluid inputs, including how much liquid you need. For example: [<liquid:water>*100].
After, there is a single bracket: [<liquid:glue>*1000, <liquid:latex>*288], which contains the fluid outputs. And the last bracket thats nulled "[]", I am not sure what is it for yet. Will update the page when I will discover it!
Anyways, thats everything you need. Bye, have a nice gregging session!
