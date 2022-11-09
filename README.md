# Sudoku-Solver
 
Problem: Solving a Sudoku Puzzle using Depth-First Search, Breadth-First Search and DFS with Heuristics. 
What is Sudoku?
Sudoku is an easy to learn logic-based number placement puzzle. The word Sudoku is short for Su-ji wa dokushin ni kagiru which means "the numbers must be single”. The roots of the Sudoku puzzle are in Switzerland. Leonhard Euler created "carré latin" in the 18h century which is like a Sudoku puzzle but without the additional constraint on the contents of individual regions. The first real Sudoku was published in 1979 and was invented by Howard Garns, an American architect. The real worldwide popularity started in Japan in 1986 after it was published and given the name Sudoku by Nikoli.
A Sudoku puzzle consists of 81 cells which are divided into nine columns, rows, and regions. The task is now to place the numbers from 1 to 9 into the empty cells in such a way that in every row, column, and 3×3 region each number appears only once.
A Sudoku has at least 17 given numbers but normally there are 22 to 30.

 
Initial State 
A standard Sudoku board, with some of the boxes filled in as specified.
Final State
A filled in Sudoku board with every row column and 3 × 3 grid having the digits 1-9.
Transition Model
Fill a box with a number. You may embody the Sudoku rules here by making the successor option return only ‘legal’ values. Using this formulation every goal state will be at the same level, though for other formulations this may not be true. The no of minimum moves required by the AI agent to solve the sudoku puzzle using the search technique.
Path Cost
The no of minimum moves required by the AI agent to solve the sudoku puzzle using the search technique.
Peas to be Defined
Performance Measure: Satisfaction of One Rule on each row, column, and block; Speed, or the shortest time at which the agent finishes the puzzle
Environment: Given the Sudoku game, the environment is given as any N x N grid with n blocks containing n cells, and some cells filled with digits chosen from 1 to n.
Actuators: String generator to display number that will satisfy the constraints.
Sensors: A scanner function that will scan rows, columns, and blocks to determine the correct number to input in blank cells

Implementing Uninformed Search Strategies in Sudoku:
Uninformed search strategies are algorithms that searches the state space for the goal state by means of a tree-traversing algorithm, without relying on other information. In this project, we are using a Depth-First Search (DFS) and Breadth-First Search (BFS) to arrive at the solution of an arbitrary Sudoku puzzle. The point of this project is not to determine the most efficient solution, but only to show an implementation of uninformed search strategies in a combinatorial puzzle. The puzzle game, along with implementations of the two search strategies, is implemented on Python.
Peter Norvig, an AI expert, wrote an essay and a program to explain how to solve any Sudoku puzzle in an efficient manner. Taking cue from the expert himself, we recognize that without using constraint propagation, that is accounting for constraints in each square, any uninformed search algorithm risks solving any given puzzle in just a few billion years. Thus, we made sure to limit the number of children of any node by applying the one-rule constraints in all tiles of a given puzzle.
Depth-First Search:
A Depth-First Search (DFS) is a tree-traversal algorithm that makes use a stack data structure to iterate through the nodes and arrive at the goal state. This is utilized in the project by adding viable states to the stack based on all the legal options in a specific square. Each last node in the stack is popped and, as a successor state, is expanded. The cycle repeats until the Sudoku grid is complete. To note, in this case, the grid is solved raster-scan style, meaning from left to right, from top to bottom, which is inefficient.

Breadth-First Search:
A Breadth-First Search (BFS) is a tree-traversal algorithm making use of a queue instead of a stack. This method makes use of horizontal expansions to cover all possibilities that may result in the Sudoku grid. With a queue method of arraying, it ensures that all nodes are addressed, however this algorithm is also time-consuming and therefore inefficient.

Utilizing heuristics:
Besides the two uninformed search strategies, heuristics can also be applied in solving any Sudoku puzzle. Common algorithms that incorporate heuristics are the A* Search and Best-First Search, both of which consider the costs of traversing one node to another to get to the goal state quickly. However, this is hard to achieve in the game of Sudoku given that a puzzle only has one solution, and it is impossible to quantify costs of each state since each action constitute to only one square answered. Therefore, we had to find other heuristic methods to complement the search techniques.
In both DFS and BFS implementations, the method of solving the board is raster-scan. Norvig suggests that in solving a Sudoku puzzle, we must choose between variable ordering and value ordering in solving a certain puzzle. Variable ordering refers to which tile should be first solved, while value ordering refers to which number should be placed in a tile first. In the case of our project, we consider variable ordering to solve puzzles more efficiently. More specifically, we utilized a similar concept to that used by Norvig, "minimum remaining values", which means that we choose a tile with the least number of possible options. This replaces the initial raster-scan method of solving and is applied to the more efficient DFS implementation.

RESULT:
In general, most puzzles were solved slower using Breadth-First Search. Depth-first Search proved to be more efficient in handling a Sudoku puzzle. If a heuristic is added in solving the puzzle, such as DFS with minimum remaining values heuristic, then the puzzle is solved in even a lesser amount of time. This project though can still be made better if other factors are used. Peter Norvig used a dictionary data structure instead of lists in making a Sudoku grid and his solutions to any problem were significantly faster than ours. He also proposes a value ordering heuristic called least-constraining value, which chooses first the value that imposes the fewest constraints on peers, and this might even improve the solution time. In addition, there are other algorithms that can be used to solve a Sudoku puzzle, some of which might even be faster (e.g., Backtracking DFS).
