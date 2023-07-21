# suduko_solver
This code is an implementation of the backtracking algorithm to solve a 9x9 Sudoku puzzle. Sudoku is a number-placement puzzle where the objective is to fill a 9x9 grid with digits so that each column, each row, and each of the nine 3x3 subgrids (boxes) contain all of the digits from 1 to 9 without repetition.

Let's go through the code step by step:

1. The given grid represents the Sudoku puzzle. The numbers from 1 to 9 are already placed in some cells, and the cells with the value 0 are the ones to be filled by the algorithm.

2. The function `printing(arr)` is a utility function used to print the grid in a readable format. It takes a 2D array `arr` as input and prints it row by row.

3. The function `isSafe(grid, row, col, num)` is a helper function to check whether it is safe to place a particular number `num` in the given `row` and `col` of the Sudoku grid. It returns `True` if it is safe to place the number; otherwise, it returns `False`.

4. The main function `solveSudoku(grid, row, col)` is a recursive function that tries to solve the Sudoku puzzle using backtracking. It takes the Sudoku grid, current `row`, and `col` as input parameters.

5. The base cases of the recursion are:
   a. If we have reached the last row and the last column of the grid, it means we have successfully filled all cells, and we return `True`.
   b. If the column value is equal to the size of the grid (9), it means we have completed the current row, so we move to the next row and reset the column to 0.

6. If the current cell of the grid is already assigned (i.e., not equal to 0), the function moves to the next column to try different possibilities.

7. If the current cell is unassigned (i.e., equal to 0), the function tries numbers from 1 to 9 to see if it's safe to place the number. If it's safe, the number is temporarily assigned, and the function makes a recursive call to the next cell (next column).

8. If the recursive call with the next column returns `True`, it means the Sudoku puzzle has been successfully solved, and the function returns `True`.

9. If the recursive call with the next column returns `False`, it means the current assumption was wrong, so the current cell is reset to 0, and the function goes back to the previous cell to try different numbers.

10. If all possibilities are tried for the current cell, and none of them lead to a solution, the function returns `False`, indicating that the current Sudoku puzzle configuration is not solvable.

11. The driver code initializes the given Sudoku grid and then calls the `solveSudoku()` function to attempt solving it. If a solution exists, the grid is printed using the `printing()` function. Otherwise, it prints "no solution exists."

Keep in mind that backtracking is an algorithmic technique for efficiently exploring all possible solutions to a problem. In this case, it helps find a valid Sudoku solution by exploring different possibilities and efficiently backtracking when a wrong assumption is made.
