CSP-Based Sudoku Solver
This project implements a Sudoku solver using Constraint Satisfaction Problem (CSP) techniques. It utilizes Backtracking search combined with the AC-3 algorithm and Forward Checking to solve puzzles ranging from Easy to "World's Hardest."

Features
AC-3 Algorithm: Pre-processes the board to ensure arc consistency, significantly reducing the search space.

Backtracking Search: Efficiently explores potential solutions.

Forward Checking: Prunes domains during search to catch dead-ends early.

MRV Heuristic: Uses the "Minimum Remaining Values" strategy to pick the next cell to fill, optimizing the solving process.

File I/O: Reads puzzles directly from .txt files for easy testing.

How to Run
Ensure you have Python 3.x installed.

Place your Sudoku puzzles in text files (e.g., easy.txt, hard.txt).

The format should be 9 lines of 9 digits, using 0 for empty cells.

Run the solver:

Bash
python sudoku_solver.py

Logic Overview
The solver follows a strict pipeline to find the solution:

Domain Building: Every empty cell starts with a domain of [1-9].

Constraint Enforcement: Using the getNeighbours function, the solver identifies all cells in the same row, column, and 3x3 box.

Consistency: The makeConsistant and AC3 functions narrow down domains before the search even starts.

Search: The backtrack function uses recursion to fill the board, using forwardCheck at every step to validate the move.

Performance Statistics
The script tracks two main metrics:

Backtrack Calls: How many times the recursive function was called.

Backtrack Failures: How many times the solver hit a dead-end and had to undo a move.

If AC-3 is powerful enough for a specific board, you might see 0 failures, meaning the logic deduced the answer without any "guessing."

## Author
Shaheer Ahmad
