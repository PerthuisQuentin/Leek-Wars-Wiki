{{Chemin|Tutoriels|Notions et stratégies}}
# Les Bulbes

Les bulbes sont les invocations de [[Leek Wars]]. Les poireaux peuvent invoquer des bulbes afin de les aider à infliger des dégâts, pour se soigner, se protéger, etc.

<img src="https://leekwars.com/image/bulb/puny_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/rocky_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/iced_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/healer_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/fire_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/wizard_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/metallic_bulb_front.png" alt="drawing" width="50"/>
<img src="https://leekwars.com/image/bulb/lightning_bulb_front.png" alt="drawing" width="50"/>

Dans le marché, les fiches des puces permettant d'invoquer un bulbe sont un peu différentes. En effet, elles présentent les caractéristiques du bulbe qui sera invoqué :

![Bulbe Chétif](/wiki/bulb.png)

Ses caractéristiques sont affichées sous la forme d'une plage de valeurs, par exemple "0 à 100 de Force". Cette valeur dépend du niveau du poireau qui invoque le bulbe. 
Un poireau de niveau 1 invoquera un bulbe avec les caractéristiques minimum. Et un poireau niveau 300 invoquera un bulbe avec les caractéristiques maximum.

Le rapport entre le niveau de l'invocateur et les caractéristiques est linéaire. C'est-à-dire que, pour "0 à 100 de Force", à chaque fois que le poireau montera de 3 niveaux, le bulbe gagnera 1 de Force.
Par exemple, au niveau 100, le bulbe aura 33 de Force, au niveau 150, il en aura 50 et au niveau 200, il en aura 66.

Remarque : Aucun bulbe n'étant débloqué au niveau 1, un bulbe n'aura jamais les statistiques les plus basses indiquées sur sa fiche.

Chaque bulbes possède 4 puces différentes que vous ne pouvez pas changer. Celles-ci varient en fonction du bulbe et possèdent les mêmes caractéristiques que celles qu'un poireau peut avoir.

Le temps de récupération d'une puce d'invocation de bulbe est commun à l'équipe. Cela ne change rien en solo, mais en éleveur ou en équipe cela signifie qu'il est impossible d'invoquer deux bulbes du même type dans un tour.



## Invocation

Si vous avez essayé d'utiliser votre bulbe avec [[useChip]], vous avez peut-être été surpris de voir que celui-ci ne faisait rien.
[[Leek Wars]] est un jeu de programmation. Vous codez l'IA de votre poireau, mais aussi de vos bulbes !

Il faudra d'abord créer une fonction qui fera office d'IA pour votre bulbe, par exemple :

```
function bulbAI() {
    var summoner = getSummoner();
    say("Bonjour, moi c'est Fab.");
    moveToward(summoner);
    useChip(CHIP_PROTEIN, summoner);
}
```

Par exemple, avec cette fonction votre bulbe suivra votre poireau pour lui donner le boost de [[Protéines]].

Dans la fonction, si vous utilisez [[getLeek]], vous obtiendrez bien l'identifiant du bulbe, et non de votre poireau. Les fonctions renvoyant des informations sur "votre poireau" renverront les informations du bulbe si elles sont dans une fonction qui sert d'IA à un bulbe.

Enfin, il faudra invoquer votre bulbe avec la fonction [[summon]]. Par exemple :

```
summon(CHIP_PUNY_BULB, cell, bulbAI);
```

Avec "cell", une cellule où vous pouvez invoquer le bulbe.

Notez qu'il faut passer en paramètre le nom de la fonction qui servira d'IA au bulbe, mais sans les parenthèses.
