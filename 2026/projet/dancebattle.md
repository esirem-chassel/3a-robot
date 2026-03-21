# Dance Battle

## Objectif général

L'objectif est de réaliser une application de "dance battle" ou "bataille de danse".

Deux robots seront placés dans une arène de 2x2 avec des couleurs aléatoires au sol.

Chaque robot va décider aléatoirement d'un nombre (défini par le serveur) de mouvements et va jouer ces mouvements, chaque robot à son tour.

En plus du mouvement effectué, le robot doit afficher une émotion, à la fois sur son expression mais aussi dans ses yeux (couleur de LED).

Lors de chaque mouvement, le robot va envoyer au serveur :
- la couleur sur laquelle il est placé
- le mouvement qu'il a effectué
- l'émotion qu'il affiche (expression et couleur de LED au format hexadécimal)

Le serveur va recevoir ces informations, et va calculer, en fonction de règles, les points obtenus pour la chorégraphie, afin de classer les deux robots.

## Applications

Deux applications doivent donc être développées :
- une application robot, qui va dérouler la chorégraphie, et envoyer les informations au serveur
- une application serveur, qui va recevoir les informations et calculer les scores

### Application Robot

L'application robot doit être capable de :
- se connecter à un robot (soit via recherche automatique, soit via la saisie d'une IP en interface)
- faire réaliser des déplacements au robot, et tester les différentes expressions
- associer une couleur relevée par le robot à une couleur standard (pour que le robot reconnaisse une plaque verte comme étant du vert)
- envoyer des informations à l'application serveur
- relever périodiquement l'état de la batterie, la couleur de la plaque
- charger un fichier .dance pour exécuter sa chorégraphie

### Application Serveur

L'application serveur doit être capable de :
- lister les robots connus
- afficher les réceptions de données de la part des robots
- charger un fichier .battle pour définir les règles de comptage de points
- afficher les points de chaque robot



### Comptage de points



## Spécifications

### Communication AppRobot <=> AppServer

Protocole HTTP
Définition d'APIs
IDs robot à la volée à la première "connexion"

### Format .dance

Ce fichier définit la chorégraphie d'un robot.
Le format est quasiment identique au `.dance` de l'activité "dancefloor".
Seul le mode séquentiel est géré, qui liste séquentiellement les mouvements, en indiquant d'abord le nombre de cases suivi de la direction "absolue".

Ce format a un élément spécifique : en seconde partie de fichier, après un indicateur "ACT", sont définies les règles d'expression du robot selon la couleur rencontrée.
Il est à noter qu'entre chaque mouvement, le robot reprend un air neutre et ses bras reviennent à la normale.

Exemple de fichier :

```
SEQ 1
1U
1L
2B
2R
1U
1L
ACT
N ARU ALB XNG
B XSD
```

### Format .battle

Ce fichier définit les points obtenus en fonction de l'association Mouvement (bras + expression) + Couleur, ainsi que les modalités de la battle.

La première partie du fichier décrit les modalités du jeu.
`MVS` donne par exemple le nombre de mouvements.

Ensuite, chaque section est indiquée via une lettre de couleur entre crochets.

Dans chaque section, on indique une combinaison par ligne avec le nombre de points attribués, en utilisant un opérateur `=` entre le mouvement et le nombre de points.

Si on souhaite indiquer une combinaison avec un opérateur ET (par exemple, pour donner des points spécifiquement si les deux bras sont en arrière), on utilise l'opérateur `+`.
Par exemple, `ALB+ARB=1` indique que si les DEUX bras sont en arrière, alors un point est attribué en plus d'autres possibles points.

Si on souhaite indiquer une liste (avec un opérateur OU), on utilise l'opérateur `,`.
Par exemple, `ALU,ARU=-1` indique que si au moins un des deux bras est levé, alors un point est retranché.
Attention, il s'agit bien d'un OU : si les deux bras sont levés, un seul point est retranché, au contraire du cas où chaque combinaison est sur une ligne.

Exemple de fichier :

```
MVS 10
[N]
ALB+ARB=1
ALU=-1
ARU=-1
ALB=1
ARB=1
XSD=1
XNG=-1
[B]
ALB,ARB,ALU,ARU=-1
XSD=2
[R]
ALU+ARU=2
ALU,ARU=1
ALB,ARB=1
XNG=3
XSD=-2
XNT=-1
```

## Annexes

### Liste des "Mouvements"

#### bras
`ALU` : Lever du bras gauche
`ARU` : Lever du bras droit
`ALB` : Bras gauche en arrière
`ARB` : Bras droit en arrière

#### Expression
`XNT` : Air neutre (repos)
`XSD` : Air triste (sourcils en bas)
`XNG` : Air énervé (sourcils en haut)

### Liste des couleurs reconnues

`N` : Noir
`P` : Mauve
`B` : Bleu foncé
`Y` : Jaune
`C` : Bleu ciel
`G` : Vert
`R` : Rouge
