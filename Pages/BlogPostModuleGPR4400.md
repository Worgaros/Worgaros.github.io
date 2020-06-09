# Blog post technique du jeu "It's mine" pour le module GPR440.2

## Remise en contexte du projet
Le jeu a été créé dans le cadre du module GPR4400.2, le module intelligence artificielle et génération procédurale de la première année de Games Programming à l’école SAE Institute Genève.

Il doit contenir une génération procédurale de la map et une IA qui se déplace sur un chemin calculer par un algorithme de pathfinding. L’IA doit également réagir en fonction du monde qui l’entoure.
 
 
## Introduction du sujet et problème à résoudre
Pour ce jeu j’ai dû créer une IA qui se déplace sur un chemin calcule par l’algorithme de pathfinding A*, un algorithme de recherche de chemin dans un graphe entre un nœud initial et un nœud final (nodes en anglais).

//image exemple A*


## Développement
### Waypoint Graph System
Pour commencer j’ai dû créer un Waypoint Graph, c’est ensemble de nodes (nœuds) reliés entre eux.

Il a d’abord fallu récupérer les deux tilemaps qui forment la map du jeu pour poser les nodes sur chaque tile:

![](https://worgaros.github.io/Images/node gen.PNG)

Texte

![](https://worgaros.github.io/Images/nodes.PNG)

Il a ensuite fallu relier les nodes voisines entre elles:

![](https://worgaros.github.io/Images/voisins.PNG)

Texte

![](https://worgaros.github.io/Images/neighbors.PNG)


### Spawn de l’IA
Dans cette étape j’ai dû faire spawner l’IA sur la map.

Dans le contexte de mon jeu, il a fallu faire spawner le joueur a la position de la node la plus en bas à droite :

![](https://worgaros.github.io/Images/spawn ia.PNG)

Texte

![](https://worgaros.github.io/Images/player spawn.PNG)


### Algo A*
Pour trouver le chemin à emprunter il a fallu utiliser l’algorithme A* :

![](https://worgaros.github.io/Images/Astar.PNG)

Texte

![](https://worgaros.github.io/Images/retrace.PNG)



![](https://worgaros.github.io/Images/go box.PNG)


### State Machine IA et fonctions
Pour que l’IA effectue des actions dans le jeu il a fallu faire une machine d’état qui lui dicte ses actions à suivre en fonctions des certains paramètres dans le jeu :

![](https://worgaros.github.io/Images/state machine.PNG)

De base on va chercher un chemin vers une boite aléatoire à ramasser sur la map :

![](https://worgaros.github.io/Images/box path.PNG)
![](https://worgaros.github.io/Images/go box.PNG)

Une fois la boite récupérée on va chercher un chemin pour la ramener au camion :

![](https://worgaros.github.io/Images/truck path.PNG)
![](https://worgaros.github.io/Images/go truck.PNG)

Quand un chemin est trouvé l’IA va l’emprunter:

![](https://worgaros.github.io/Images/go box.PNG)
![](https://worgaros.github.io/Images/go box.PNG)
![](https://worgaros.github.io/Images/follow path fonction.PNG)
![](https://worgaros.github.io/Images/follow path.gif)


## Conclusion
 Pour conclure, l’algorithme A* de ce projet peut être utilise dans d’autre jeux comme par exemple un jeu qui n’utilise pas de tilemap. Il faudrait mettre à la main les nodes un par un.


## Sources et liens
### Image utilise dans ce document :
[https://media.geeksforgeeks.org/wp-content/uploads/a_-search-algorithm-1.png]( https://media.geeksforgeeks.org/wp-content/uploads/a_-search-algorithm-1.png)


### Tutoriel suivit :
[https://youtu.be/AKKpPmxx07w](https://youtu.be/AKKpPmxx07w)


### Lien du repo GitHub du projet:
[https://github.com/eleonoradps/ItsMine]( https://github.com/eleonoradps/ItsMine)


### [Retour à la page principale](https://worgaros.github.io/)
