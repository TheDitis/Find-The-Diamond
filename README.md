# Find-The-Diamond
Find the diamond on an NxN grid using directional hits.

First the grid (numpy array) is created, and then a 'diamond' is randomly assigned to a point on the grid.
Every time you guess incorrectly you will get a directional clue in the form of N, SE, NW, etc.

each point of the grid is represented with a list of 3 numbers, initialized as [0, 0, 0]
index 0 is the N/S indicator with 1 being N and -1 being S. index 1 is the same for E/W with 1 being E and -1 being W
index 2 is a binary indicator for the diamond. all are zeros except the randomly placed diamond

set_hints() runs through the program of empty points and sets the N/S & E/W indicators according to the relative location of the diamond

cardinal_direction(coordinates) reads the indicators of a point and turns it into a readable direction

where_to is used by auto_solve to tell it where to go next. The idea is that it guesses right in the middle of the grid, and then it guesses in the middle of the quadrant that the directional clue indicates, reducing the search area by 1/4 each guess. where_to tells it whether to add or subtract the difference between the last guess and the current, and which coordinate(s) to apply it to.

auto_solve iterates through where_to some number of times, feeding back to itself its’ new suggested cardinal direction, its’ guess from last time, and its new coordinates to check. It prints out the direction and the coordinates it is trying until it strikes diamond.
