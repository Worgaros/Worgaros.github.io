# AI in Unreal Engine for Voliday

## Introduction

### Context

During my 3rd year of Games Programming at SAE Institute Geneva, I had to participate in a specialization project where we had to create a City Builder game on Unreal Engine 4 playable on PC with an art direction close to The Legend of Zelda: Link's Awakening. I mainly had to work on the AI of this game, called Voliday, which are tourists coming to spend their holidays on an island where they perform activities. 
To create the AIs we used a behavior tree and a blackboard from Unreal Engine 4.

## Definitions

- A behavior tree is a mathematical model of plan execution.
- Values used in the behavior tree are stored in the blackboard.
- Tasks are nodes that do things like move the AI or adjust blackboard values.

## Development

Taking over another member’s work
I took the AI already started by one of my classmates, the AI is composed of a controller that manages everything the AI has to do and this is linked to an AI character which is the visual model of the AI. In order for the AI to perform actions according to certain parameters, my classmate used a behavior tree along with his blackboard. The AI would randomly choose a position on a navmesh and go there, then wait a few seconds and repeat the process.

### Revising the actions of AI

I modified the behavior tree by starting, at the arrival of the AI on the island, by giving to variables of the blackboard the position of its dwelling chosen randomly but by taking into account if it is a rich or poor and also the position of the port so that it can return there to leave the island while taking into account to distribute them well according to the available places.

image debut

Then I kept the system of the task which sends towards a destination which this time takes into account the position of the building. Once there, the AI pays for its stay and then waits before randomly choosing one of the activities that is allowed and accessible. Then it goes there and waits before paying the price of the activity.

image milieu

Then there is a check if the AI still has enough money it continues to perform the loop of activities until it has none left. If it has more, it goes to the port or despawns to simulate its departure.

image fin

Here is a complete overview of the order of the behavior tree’s task:

image tout

I handed over my AI task to a colleague so I could work on something else.

### Resume back my classmate work

I was surprised when I came back to take over my AI task, because my colleague redid the whole behavior tree. After discussion it was due to the fact that the way he told me to do it was not optimal to add satisfaction to the AI. I should have asked the game designer before I started. Fearing that I wouldn't have the time to figure out how to do it, and without asking me for help, he decided to redo it to figure it all out and add satisfaction to the AIs.
After taking the time to understand with his help how he made the behavior tree, I added the fact that the AI instead of choosing a house randomly it chooses the house with the least amount of people in it. I then replaced the AI model which was a white cone with the model given by the Game Art students while waiting for Vincent to add the animations. I then corrected two major bugs which were that if you delete some buildings the AI would get stuck because it couldn't continue to browse the behavior tree, so I forced it to continue to browse the behavior tree at those times so it wouldn't get stuck. The second bug was that when you pause the game the AI if the AI was in a waiting task it would even pause the satisfaction and spending tasks, to avoid this I put the waiting task at the end so that the behavior tree would pause directly after it.

## Difficulties encountered

One of the difficulties was to understand how the behavior tree and its blackboard work in Unreal Engine 4. Also to take over the work started by someone else.

## What I learned

I learned that it is important to have a clear understanding of all the tasks required and to comment on your code to avoid having your code replaced by someone else. It's very important to talk to each other face to face to resolve our conflicts and understand how we got there so that we don't make the same mistakes the next time. But also to warn the person who takes over the job that they should not hesitate to come and ask for explanations if it is not understandable.

## Conclusion
To conclude, it is very important to be sure to understand the tasks you have to accomplish and also to discuss when there are problems to solve them as soon as possible.


### [Retour à la page principale](https://worgaros.github.io/)

Exemple image
![](https://worgaros.github.io/Images/openwin.gif)