# Blog post technique du moteur physique" pour le module GPR4400

## Remise en contexte du projet
Le jeu a été créé dans le cadre du module GPR4400.1, le module moteur physique de la première année de Games Programming à l’école SAE Institute Genève.

Le moteur doit pouvoir générer de la physique rigide en 2D. Il doit y avoir différents type de body (statique, dynamique et cinématique), des collision et des trigger pour différentes formes (box, cercle et polygone), une implémentation de bounding volume (AABB), du space partitioning (QuadTree) et des corrections de de position et vélocités après collision.

## Développement
### Détection de collision entre AABB
Il a d’abord fallu faire une fonction qui regarde si deux AABB se superpose:

![](https://worgaros.github.io/Images/AABB.PNG)

Il a ensuite fallu faire des fonctions pour créer les AABB pour les 3 formes différentes (Box, cercle et polygone):

![](https://worgaros.github.io/Images/shapeBox.PNG)
![](https://worgaros.github.io/Images/shapeCircle.PNG)
![](https://worgaros.github.io/Images/shapePolygon.PNG)

Ensuite il a fallu regarder le type de forme entre les deux objets pour ensuite voire si leurs AABB se superposent:

![](https://worgaros.github.io/Images/contact.PNG)

Pour finir il a fallu changer la couleur des colliders des objets dont leurs AABB se superposent:

![](https://worgaros.github.io/Images/color.PNG)

Voici un aperçu du résultat :

![](https://worgaros.github.io/Images/pascol.PNG)
![](https://worgaros.github.io/Images/col.PNG)

### Ce qu’il reste à faire
#### SAT
Il faut faire les SAT entre les différentes formes pour qu’une fois la collision entre deux AABB est confirmée on puisse vérifier s’il y a collision entre les colliders des deux objets et également obtenir le MTV.

#### QuadTree
Il faut faire un QuadTree pour pouvoir séparer en plusieurs parties les objets pour pouvoir gérer les collisions quand il y a beaucoup d’objets en même temps.

#### Restitution
Il faut pour finir, en fonction du MTV reçu, recalculer la position, la direction et la vélocité des objets après collision.

## Conclusion



## Liens
[https://box2d.org/documentation/index.html](https://box2d.org/documentation/index.html)
[https://developer.mozilla.org/en-US/docs/Games/Techniques/2D_collision_detection](https://developer.mozilla.org/en-US/docs/Games/Techniques/2D_collision_detection)


### [Retour à la page principale](https://worgaros.github.io/)
