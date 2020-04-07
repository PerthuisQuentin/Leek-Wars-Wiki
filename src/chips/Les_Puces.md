
{{Chemin|Tutoriels|Notions et stratégies}}
# Les Puces

Dans [[Leek Wars]], les poireaux peuvent utiliser des puces. Ce sont des objets qui permettent d'attaquer, de soigner, de se protéger, de booster, d'entraver, etc.

Contrairement aux armes, les puces n'ont pas besoin d'être prises en main. Si une puce est équipée sur votre poireau, il peut l'utiliser directement via la fonction [[useChip]] (ou [[summon]] pour une puce d'invocation). Il n'y a pas besoin de la "prendre en main" avec une fonction comme [[setWeapon]].

Si elles offrent ainsi plus de liberté que les armes, certains puces sont par contre soumises à un temps de '''récupération''', aussi appelé '''cooldown'''. Si une puce indique "Récupération : 3 tours", cela signifie que lorsque vous utiliser la puce, vous devez attendre 3 tours avant de pouvoir la réutiliser. Les fonctions [[getCooldown]] et [[getChipCooldown]] vous permettront d'obtenir des informations sur ce '''cooldown''' dans votre code.


Certaines puces ont la particularité de ne pouvoir être utilisées qu'en ligne. Pour savoir si une puce s'utilise en ligne, on utilise la fonction [[isInlineChip]].
Il faudra donc être aligné avec la cible pour utiliser ces puces, ce qui peut peut se vérifier avec la fonction [[isOnSameLine]].

On distingue deux types de puces :

* Armes à cible unique : Elles ne touchent qu'une cellule.

* Armes à cibles multiples : Ces puces peuvent toucher plusieurs cellules à la fois. On parle d''''aire d'effet''' (ou '''AoE'''). [[Aire d'effet | Plus d'explications sur les aires d'effet]]


Depuis la version 2.9.0, un poireau au niveau maximum peut avoir jusqu'à 20 puces équipées. Au niveau 1, il ne peut en équiper que 12. À partir  niveau 50, il pourra en équiper une supplémentaire et ainsi de suite:

| Tranche de niveau | Puces équipables  |
|-------------------|-------------------|
| Niveau 1 à 49     | 12 puces          |
| Niveau 50 à 74    | 13 puces          |
| Niveau 75 à 99    | 14 puces          |
| Niveau 100 à 124  | 15 puces          |
| Niveau 125 à 149  | 16 puces          |
| Niveau 150 à 199  | 17 puces          |
| Niveau 200 à 249  | 18 puces          |
| Niveau 250 à 299  | 19 puces          |
| Niveau 300 à 301  | 20 puces          |

# Liste des puces