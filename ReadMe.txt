Maze Generator by unionning graphs

Considering this "maze under construction" where every " - " is a node.

1 2 3 4 5 6 7 8 9 ..    13
+---+---+---+---+---+---+ 1
| - | - | - | - | - | - | 2
+---+---+---+---+---+---+ 3 
| - | - | - | - | - | - | 4
+---+---+---+---+---+---+ 5
| - | - | - | - | - | - | 6
+---+---+---+---+---+---+ 7
| - | - | - | - | - | - | ...
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+ 13

We add the center node to the vector 'a' which has all the nodes that have neighbours and are not in 'a'.
while a is not empty, we choose a random node from 'a' and put in a vector 'vec' all its adiacent nodes that are not in 'a'.
We choose randomly a node from 'vec' and add him to 'a' while "breaking the wall between these 2 nodes.

1 2 3 4 5 6 7 8 9 ..    13
+---+---+---+---+---+---+ 1
| - | - | - | - | - | - | 2
+---+---+---+---+---+---+ 3 
| - | - | - | - | - | - | 4
+---+---+---+---+---+---+ 5
| - | - |       | - | - | 6
+---+---+---+---+---+---+ 7
| - | - | - | - | - | - | ...
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+ 13

Repeat until there is only one graph

1 2 3 4 5 6 7 8 9 ..    13
+---+---+---+---+---+---+ 1
| - | - | - | - | - | - | 2
+---+---+---+---+---+---+ 3 
| - | - | - | - | - | - | 4
+---+---+---+---+---+---+ 5
| - | - |       | - | - | 6
+---+---+---+   +---+---+ 7
| - | - | - |   | - | - | ...
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+
| - | - | - | - | - | - |
+---+---+---+---+---+---+ 13


...

1 2 3 4 5 6 7 8 9 ..    13
+---+---+---+---+---+---+ 1
|   |       |           | 2
+   +---+   +   +   +---+ 3
|           |   |       | 4
+---+---+   +---+---+   + 5
|       |           |   | 6
+   +---+   +   +---+   + 7
|           |           | 8
+   +---+---+---+   +---+ 9
|       |       |       | 10
+   +---+   +---+   +---+ 11
|       |               | 12
+---+---+---+---+---+---+ 13

And then solve it using backtracking

1 2 3 4 5 6 7 8 9 ..    13
+---+---+---+---+---+---+ 1
|   |       |     >   >   2
+   +---+   +   +   +---+ 3
|           |   | ^   < | 4
+---+---+   +---+---+   + 5
|       | >   v     | ^ | 6
+   +---+   +   +---+   + 7
| >   >   ^ | >   >   ^ | 8
+   +---+---+---+   +---+ 9
| ^     |       |       | 10
+   +---+   +---+   +---+ 11
  ^     |               | 12
+---+---+---+---+---+---+ 13
