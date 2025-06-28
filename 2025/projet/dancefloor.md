# Projet Dancefloor

## Consignes


## Objectif général

L'objectif est de réaliser un programme de commande d'un robot dans l'optique de lui permettre de danser et d'effectuer des actions selon les plaques de couleur rencontrées.
Un fichier .feels permet de faire le lien entre la plaque de couleur rencontrée et l'émotion exprimée à ce moment, ainsi que la couleur des LEDs.
Un fichier .dance permet d'indiquer au robot la chorégraphie qu'il doit suivre : ses pas de danse.


## Possibilités du programme

On doit pouvoir, depuis l'interface du programme principal :
- calibrer la reconnaissance de couleurs, qui doit se faire manuellement au début de chaque test, afin d'associer chaque plaque à une couleur
- se connecter au robot via son IP
- visualiser les capteurs disponibles : couleur, batterie, obstacle...
- effectuer des ordres manuels : avancer, remuer...
- charger un fichier .feels
- charger un fichier .dance et visualiser/exécuter les commandes correspondantes


## Extensions

### Génération du .feels
Votre programme doit disposer d'une interface sous la forme d'un tableau (ou toute interface pertinente, et non un bloc-notes)
pour associer une couleur reconnue (avec son nom) d'une émotion et d'une représentation hexadécimale de couleur de LEDs.

### Génération du .dance
Votre programme doit disposer d'une interface afin de donner les ordres au robot,
qui seront ensuite utilisés pour générer un fichier .dance qu'on pourra nommer,
toujours via l'interface.

### Génération du .calib
Votre programme doit être capable de sauvegarder sa calibration actuelle de couleurs sous la forme d'un fichier .calib qu'on pourra nommer via l'interface.
De même, votre interface devra donner la possibilité de charger un fichier .calib pour calibrer automatiquement une reconnaissance de couleurs.

### Pilotage sensitif
Votre programme devra être capable d'afficher une petite interface avec une zone sensitive (avec laquelle on peut agir via cliquer/glisser)
pour permettre le déplacement du robot en fonction des gestes effectués sur cette interface.


## Annexes

### Documentation Python pour Marty

### PyQT6

### Format .feels

### Format .dance

### Format .calib
