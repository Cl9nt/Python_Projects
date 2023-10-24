## Snakes and Ladders

### Question

You are given an *n x n* integer matrix *board* where the cells are labeled from *1 to n2* in a **Boustrophedon style** starting from the bottom left of the board (i.e. *board[n - 1][0])* and alternating direction each row.

You start on square *1* of the board. In each move, starting from square *curr*, do the following:

Choose a destination square *next* with a label in the range *[curr + 1, min(curr + 6, n2)]*.
    
This choice simulates the result of a standard 6-sided die roll: i.e., there are always at most 6 destinations, regardless of the size of the board.

If *next* has a snake or ladder, you must move to the destination of that snake or ladder. Otherwise, you move to *next*.
    
The game ends when you reach the square *n2*.

A board square on row *r* and column *c* has a snake or ladder if *board[r][c] != -1.* The destination of that snake or ladder is *board[r][c]*. Squares *1* and *n2* do not have a snake or ladder.

Note that you only take a snake or ladder at most once per move. If the destination to a snake or ladder is the start of another snake or ladder, you do not follow the subsequent snake or ladder.

For example, suppose the board is *[[-1,4],[-1,3]]*, and on the first move, your destination square is *2*. You follow the ladder to square *3*, but do not follow the subsequent ladder to *4*.

Return the least number of moves required to reach the square *n2*. If it is not possible to reach the square, return *-1*.

#### Implementation

Using Breadth-First Search (BFS) algorithm.

It takes int account the unique layout of the board, which follows a Boustrophedon pattern, and considers the presence of snakes and ladders.

The algorithm converts square numbers to row and column coordinates to simulate the player's movement. It maintains a queue of possible moves, exploring them step by step while keeping track of the minimum number of moves required to reach each square.

The process continues until it either reaches the target square (n^2) or determines that it's impossible to reach the last square, returning the minimum number of moves required or -1, respectively.