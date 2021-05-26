# InstantInsanity_Triangular
Attempt to solve an instant insanity puzzle with puzzle pieces in the shape of triangles, where ever face is an opposite face
## About
This program solves for a puzzle of up to a size of 30 stacked slices.

The puzzle is considered solved when the stack of 30 triangular slices with colored sides contain no more than 1 of each color per side of the entire stack.
In other words every silce on each side of the stack must have a uniqe color for that side of the stack. And all 3 sides of the entire stack must satisfy this condition

If the program fails to find a solution it will find the minimum obstacle which is defined as the smallest set of slices that cannot be solved making the whole puzzle unsolvable.

This program and puzzle are a variation of the Cube shaped Instant Insanity Problem

## Requirements
Python 3.0
## Design
The algorithm is a DFS/BFS style algorithm that prioritizes slice rotation positions which can be
successfully added to the solution space (no interference) for any given slice in the stack
If at anypoint, the current slice the algorithm is working on cannot be added to the solution
space--on any of the slices 3 rotation positions--the algorithm will backtrack to the previous slice
added to the solution and rotate it to a new position such that it fits the solution space.
If the algorithm finds new valid rotation, it will proceed with the next slice; otherwise it will
backtrack again.
The algorithm terminates when all slices for the current stack have been added to the solution
space, or if the algorithm backtracks back to top of the stack and must back-track once more--
meaning no possible combinations of slice rotations for the stack exist that satisfy a solution.
The algorithm is the heart of our code and can be found as the solve() function in our source
code.
