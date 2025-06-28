# Survey - Validation 2024/2025

## Consignes

Vous pouvez réutiliser autant de code de votre projet original que vous souhaitez.

L'accès à Internet, à Github est autorisé.

L'usage d'IA est interdite.

L'avancée dans l'activité sera notée, ainsi que l'ensemble des compétences en lien avec le projet robotique (bonnes pratiques, programmation, structuration...).


## Interface initiale

Affichage d'une interface de base :
- une unique fenêtre 
- en haut de cette fenêtre, trois éléments
- - un libellé indiquant l'état (connecté ou non)
- - un champ de texte
- - un bouton de connexion (si déconnecté) ou déconnexion (si connecté)
- au centre, un unique libellé nommé "middle_cmd"

## Actions du robot

Les actions attendues sont les suivantes :
- lors du démarrage du programme, celui-ci va lire et charger un fichier "survey.traj" en mémoire
- - si aucun fichier n'est trouvé, une erreur doit s'afficher dans la console sans terminer le programme
- lorsque le bouton "connexion" est utilisé, si une IP est saisie, le programme essayera de se connecter au robot
- - si la connexion ne se réalise pas, une erreur doit s'afficher dans la console sans terminer le programme
- - si la connexion se réalise bien, le libellé indiqué l'état doit changer, ainsi que le bouton de connexion
- une fois connecté au robot, le libellé "middle_cmd" doit afficher une couleur verte si aucun obstacle n'a été détecté, rouge si un obstacle est détecté
- le robot doit ensuite exécuter les commandes données par le fichier "survey.traj"
- pendant l'exécution des commandes, le libellé "middle_cmd" doit continuer à fonctionner

# Annexes

## Format du fichier .traj

Ce fichier contient une liste d'instructions (une instruction par ligne) devant être réalisées par votre robot.

- FW : le robot doit avancer de X pas
- BW : le robot doit reculer de X pas
- LT : le robot doit faire un pas chassé à gauche de X pas
- RT : le robot doit faire un pas chassé à droite de X pas

