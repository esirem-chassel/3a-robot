# Dance Battle

## Objectif général

L'objectif est de réaliser une application de "dance battle" ou "bataille de danse".

Deux robots seront placés dans une arène de 3x3 avec des couleurs aléatoires au sol.

Chaque robot va décider aléatoirement d'un nombre (défini par le serveur) de mouvements et va jouer ces mouvements, chaque robot à son tour.

En plus du mouvement effectué, le robot doit afficher une émotion, à la fois sur son expression mais aussi dans ses yeux (couleur de LED).

Lors de chaque mouvement, le robot va envoyer au serveur :
- la couleur sur laquelle il est placé
- le mouvement qu'il a effectué
- l'émotion qu'il affiche (expression et couleur de LED au format hexadécimal)



### Règles spécifiques

Un robot qui rentre en collision dans un autre robot est disqualifié.
Chaque robot doit s'assurer, soit au moyen de calculs soit au moyen d'une détection d'obstacles, de ne pas heurter l'autre robot.


### Comptage de points



## Spécifications

Note : quand on parle de "serveur", on parle ici de l'application elle-même.

## Annexes

### Format 
