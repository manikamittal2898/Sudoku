# Sudoku
The concept of Sudoku is simple. The game is most frequently a 9x9 grid made up of 3x3 sub-grids. Some cells already contain numbers, known as "givens". The goal is to fill in the empty cells, one number in each, so that each column, row, and region contains the numbers 1 through 9 exactly once.  The main key to have to help solve these puzzles is patience and your use of logic skills. It is not just a case of trial and error to get the right result. Following is an example puzzle.

•	The Sudoku solver solves the Sudoku puzzle by creating a list of possible values for each cell, i.e. the already filled cells have their fixed value in the list while the empty cells have numbers from 1-9 in their list initially. All these lists are stored in a n*n String array

•	Then the solver applies 3 constraints to reduce the list of possible values of each grid cell. The three constraints used are: 
o	The elimination strategy
o	The only choice strategy
o	The naked- twins strategy

•	Elimination strategy- This constraint function goes through all of the cells with known values and eliminates those values from the lists of possible values of all its peers. Peers of a cell are the cells which occur in the same column or same row or same sub grid as the given cell.

•	The Only Choice strategy- This constraint function iterates through all the rows/cols/sub grids and if there's a particular number that fits in only one cell in a particular row/col/sub grid then that value is fixed in that particular grid cell. This function checks all rows, all columns and all sub grids for all 1-9 numbers.

•	The Naked Twins strategy- This constraint function applies the heuristic- naked twins to further reduce the search space. This function ensures that if in a particular row/col/sub grid, there are two cells that have the same two possible values (naked twins) then those two values will certainly be in those two boxes and so can be removed from the other boxes in the row/col/sub grid. 

•	Backtracking - After the search space is reduced the maximum it can be, we apply backtracking and start assigning numbers to empty cells from their respective lists. Before assigning a number, we check whether it is safe to assign. We basically check that the same number is not present in the current row, current column and current 3X3 sub grid. After checking for safety, we assign the number, and recursively check whether this assignment leads to a solution or not. If the assignment doesn’t lead to a solution, then we try the next number for the current empty cell. And if none of the number (1 to 9) leads to a solution, we return false.

