# AntWars
This project simulates a game in which a 2D grid is populated with ants and beetles (based on a file being read).  The game plays against itself.

The game is a simple, casual game where players try to avoid their ant colony being destroyed by an invading colony of 
beetles. The player will have an opportunity to play against an AI or against another player. You have been assigned to 
help develop the AI part of the game. 

Game Details:

-The game will be played on a 10 x 10 grid
-Beetles will move before the ants
-A file will be used to populate the grid (a = ant, B = beetle)
-Grid traversal should be by column first then row
-Creatures to the left perform actions before creatures to the right
-User will specify number of turns to watch
-All movement is orthogonal (N, S, E, W)
-Movement is limited to one space per turn
-Movement happens before breeding and starving
-A beetle will eat an ant if it moves into the same space as the ant

The Ant and Beetle class have their own specifications.  They are as follows:

Ant Details:
Move
  o Each ant will move in the opposite direction of the nearest orthogonal beetle
  o If no beetle, ant stands still
  o If multiple beetles are nearest, prioritize movement
  o Move ant in direction of no beetle if possible
  o If beetles in all directions, move toward farthest beetle
  o Cannot move to occupied space
  o If space moving to is occupied, no movement happens
  o Cannot move off grid
Breed
 o If ant survives 3 turns, it breeds
 o Add ant in adjacent orthogonal space
 o Start with north space and check clockwise around space until empty orthogonal space found
 o If no empty spaces, no breeding
 o Ant may not breed again unless it survives another 3 turns
 
Beetle Details:
Move
 o Move toward nearest orthogonal ant
 o If multiple ants are nearest prioritize movement
 o Move toward ant with most adjacent ant neighbors (orthogonal and diagonal)
 o If still tied, move toward ant with most ant neighbors using the following priority: N, E, S, W
 o If no ant, move toward farthest edge

Breed
o If beetle survives for 8 turns, it breeds
o Use breeding algorithm for ants
o Beetle cannot breed again unless it survives another 8 turns

Starve
o If a beetle does not eat an ant in 5 turns, it dies

User Interface: The only user interface will be the user entering the number of turns for the simulation.
The initial grid will be populated from file input. The file will be named world.txt. 
Output: All output will be sent to the console. Print the current state of the grid to the console window. The simulation 
pauses after each turn. Have the user press enter to start the next turn.
