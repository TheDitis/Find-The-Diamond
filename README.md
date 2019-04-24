# Find-The-Diamond
Find the diamond on an NxN grid using directional hits.

First the grid (numpy array) is created, and then a 'diamond' is randomly assigned to a point on the grid.
Every time you guess incorrectly you will get a directional clue in the form of N, SE, NW, etc.

each point of the grid is represented with a list of 3 numbers, initialized as [0, 0, 0]
index 0 is the N/S indicator with 1 being N and -1 being S. index 1 is the same for E/W with 1 being E and -1 being W
index 2 is a binary indicator for the diamond. all are zeros except the randomly placed diamond

set_hints() runs through the program of empty points and sets the N/S & E/W indicators according to the relative location of the diamond

cardinal_direction(coordinates) reads the indicators of a point and turns it into a readable direction


