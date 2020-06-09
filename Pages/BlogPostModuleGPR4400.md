# Blog post technique du jeu "It's mine" pour le module GPR440.2

## Remise en contexte du projet
Le jeu a été créé dans le cadre du module GPR4400.2, le module intelligence artificielle et génération procédurale de la première année de Games Programming à l’école SAE Institute Genève.

Il doit contenir une génération procédurale de la map et une IA qui se déplace sur un chemin calculer par un algorithme de pathfinding. L’IA doit également réagir en fonction du monde qui l’entoure.
 
 
## Introduction du sujet et problème à résoudre
Pour ce jeu j’ai dû créer une IA qui se déplace sur un chemin calcule par l’algorithme de pathfinding A*, un algorithme de recherche de chemin dans un graphe entre un nœud initial et un nœud final (nodes en anglais).

Voici un exemple visuel de l’algorithme :

![](https://worgaros.github.io/Images/Astar ex.png)


## Développement
### Waypoint Graph System
Pour commencer j’ai dû créer un Waypoint Graph, c’est ensemble de nodes (nœuds) reliés entre eux.

Il a d’abord fallu récupérer les deux tilemaps qui forment la map du jeu pour poser les nodes sur chaque tile:

![](https://worgaros.github.io/Images/recup tilemap.PNG)

Ici on récupère les tilemaps ou sont généré procéduralement les tiles formant une map avec des murs dans l’une des tilemaps et le sol dans l’autre.

![](https://worgaros.github.io/Images/node gen.PNG)

Ici on place une node sur la position de chaque tile, on les met toutes en non libres (l’IA ne pourra pas marcher sur ces tiles) et l’on met ensuite toute les nodes qui sont sur des position de tile de la tilemap du sol en libre.

Voici un visuel du résultat:

![](https://worgaros.github.io/Images/nodes.PNG)

Il a ensuite fallu relier les nodes voisines entre elles:

![](https://worgaros.github.io/Images/voisins.PNG)

Ici on regarde pour chaque node si on peut faire des raycast en direction des nodes autour d’elle et si le raycast ne rentre pas en contact avec un collider et que c’est une node libre on la rajoute à ses voisins.

Voici un exemple visuel du résultat:

![](https://worgaros.github.io/Images/neighbors.PNG)


### Spawn de l’IA
Dans cette étape j’ai dû faire spawner l’IA sur la map.

Dans le contexte de mon jeu, il a fallu faire spawner le joueur a la position de la node la plus en bas à droite :

![](https://worgaros.github.io/Images/spawn ia.PNG)

Voici un exemple visuel du résultat:

![](https://worgaros.github.io/Images/player spawn.PNG)


### Algo A*
Pour trouver le chemin à emprunter il a fallu utiliser l’algorithme A* :

![](https://worgaros.github.io/Images/Astar.PNG)

Ici on regarde le cout de trajet vers les nodes qui entoure la node actuelle (on commence par la node de départ) puis on regarde si la node n’est pas la node que l’on veut atteindre.

Si la node actuelle n’est pas la node d’arrivée on rajoute au cout le cout de l’heuristique qui est la distance entre la node actuelle et la node d’arrivée ce qui permet à l’algorithme de tendre plus rapidement vers la node d’arrivée.

On effectue ça en prenant chaque node voisine ayant le moins de cout jusqu’à arriver a la node objectif.


![](https://worgaros.github.io/Images/retrace.PNG)

Quand on atteint la node finale cette fonction retrace toute les nodes du chemin trouvé pour s’ajouter entre elles en parents (cela permettra à l’IA de se déplacer en allant de parent en parent)

Voici un exemple visuel du résultat:

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

![](https://worgaros.github.io/Images/follow path code.PNG)
![](https://worgaros.github.io/Images/follow path fonction.PNG)
![](https://worgaros.github.io/Images/follow path.gif)


## Conclusion
 Pour conclure, l’algorithme A* de ce projet peut être utilise dans d’autre jeux comme par exemple un jeu qui n’utilise pas de tilemap. Il faudrait mettre à la main les nodes un par un.


## Sources et liens
### Image utilisée dans ce document :
[https://media.geeksforgeeks.org/wp-content/uploads/a_-search-algorithm-1.png]( https://media.geeksforgeeks.org/wp-content/uploads/a_-search-algorithm-1.png)


### Tutoriel suivit :
[https://youtu.be/AKKpPmxx07w](https://youtu.be/AKKpPmxx07w)


### Lien du repo GitHub du projet:
[https://github.com/eleonoradps/ItsMine]( https://github.com/eleonoradps/ItsMine)


### [Retour à la page principale](https://worgaros.github.io/)
