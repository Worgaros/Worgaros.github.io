# GDD Neko Networking - Cars Soccer 

## Introduction
 Cars Soccer is a multiplayer online game which you play a car.
 You have to score goals, the first to 5 win.
 
## 3C
* It's a top down game and the camera is fixed.
The player can move from top to bottom and from left to right but can't turn.
To move the player have to use wasd keys.

![](https://worgaros.github.io/Images/game.png)

## Physique
* When a car touch the ball, the ball take his velocity and direction.
If two cars touch it, the ball take both velocity and go in a perpendicular direction of cars direction.
The ball slowed down until it stops.
When both cars make contact the fastest destroy the other.
If both cars have same velocity, they both explode.
When a car explode the player have to wait 2 seconds to be able to move his car.
When the ball touch the left or the right wall a car score a goal and both cars and the ball respawn a the same positions at the start of the game.
If the ball touch the top or bottom wall the ball inverse the y of this direction.

## Networking
* I have to do create and destroy functions to be able to respawn cars or the ball if it's detroy or created before the last validate frame.
I have to modify some controls inputs in the input manager.
I have to change game rules in the game manager.


### [Retour à la page principale](https://worgaros.github.io/)