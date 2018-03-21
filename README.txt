Backtracking Depth-first-search solution:

With possible movements into (down, right) cells, we recursively call the down and right cells. At every point, we add the sum contributed by the cell(sum of adjacent negative cells(Down , Right, Left, Up). While backtracking, we gather the sums storing them in a hashmap. The eventual solution will be a sorted response from this hashmap. Since at every cell(n^2), we can possibly call O(n^2) cells through down and right movement. Thus, time complexity is O(n^4). Space complexity is O(n^2), due to the list of lists stored during backtracking, as well as the O(n^2) used by Python for performing recursion. A possible optimization to store the the final result for each cell in the matrix. This will make sure that we don't call for the same cell again, through another traversal path. Average case will improve, however worst case will still be O(n^4). Simple implementation is to add a map of list of paths for each element in the matrix.

Procedure: 
Function: generateMatrix():
Generated random matrices with fixed sizes of 3,4,5,6 (we can add more numbers to create more matrices). Test cases, there aren't possible tricky corner cases to specifically add for the generator.  

Function: printMat(matrix):
Function to print a matrix

Function: getThisEl(matrix,i,j):
Get the off path adjacent values

Function: travn4(i,j,matrix,listSoFar,sumSoFar,ret):
DFS function

Function: ea1(matrix):
Main function that calls dfs, and sorts list of lists of paths

Inputs and Outputs:

[6, 5, 15]
[-5, 14, 12]
[2, 15, -1]
------
defaultdict(<class 'list'>, {})
[]
------
[3, 14, 3, 1]
[8, -1, 11, 6]
[15, -2, 1, 15]
[-1, 1, 3, 7]
------
[3, 14, 3, 11, 1, 3]
[3, 14, 3, 11, 1, 15]
[3, 14, 3, 11, 6, 15]
[3, 14, 3, 1, 6, 15]
defaultdict(<class 'list'>, {-4: [[3, 14, 3, 11, 1, 3], [3, 14, 3, 11, 1, 15]], -2: [[3, 14, 3, 11, 6, 15]], -1: [[3, 14, 3, 1, 6, 15]]})
[[3, 14, 3, 11, 1, 3], [3, 14, 3, 11, 1, 15], [3, 14, 3, 11, 6, 15], [3, 14, 3, 1, 6, 15]]
------
[13, -1, -4, 6, -1]
[14, -1, -3, 2, 1]
[-3, 14, 3, 0, -2]
[14, -4, 12, -4, 5]
[10, -3, -3, -2, -4]
------
defaultdict(<class 'list'>, {})
[]
------
[7, 11, -1, 13, 6, 5]
[2, -5, 13, 11, 9, 1]
[13, 2, 7, -5, 3, 4]
[-2, -2, 6, 6, -2, -5]
[5, 11, 2, 13, 8, 6]
[-4, 3, 3, 13, 7, 7]
------
[7, 2, 13, 2, 7, 6, 2, 3, 13, 7]
[7, 2, 13, 2, 7, 6, 2, 13, 13, 7]
[7, 2, 13, 2, 7, 6, 2, 13, 8, 7]
[7, 2, 13, 2, 7, 6, 2, 13, 8, 6]
[7, 2, 13, 2, 7, 6, 6, 13, 13, 7]
[7, 2, 13, 2, 7, 6, 6, 13, 8, 7]
[7, 2, 13, 2, 7, 6, 6, 13, 8, 6]
defaultdict(<class 'list'>, {-21: [[7, 2, 13, 2, 7, 6, 2, 3, 13, 7], [7, 2, 13, 2, 7, 6, 2, 13, 13, 7]], -23: [[7, 2, 13, 2, 7, 6, 2, 13, 8, 7]], -28: [[7, 2, 13, 2, 7, 6, 2, 13, 8, 6], [7, 2, 13, 2, 7, 6, 6, 13, 13, 7]], -30: [[7, 2, 13, 2, 7, 6, 6, 13, 8, 7]], -35: [[7, 2, 13, 2, 7, 6, 6, 13, 8, 6]]})
[[7, 2, 13, 2, 7, 6, 6, 13, 8, 6], [7, 2, 13, 2, 7, 6, 6, 13, 8, 7], [7, 2, 13, 2, 7, 6, 2, 13, 8, 6], [7, 2, 13, 2, 7, 6, 6, 13, 13, 7], [7, 2, 13, 2, 7, 6, 2, 13, 8, 7], [7, 2, 13, 2, 7, 6, 2, 3, 13, 7], [7, 2, 13, 2, 7, 6, 2, 13, 13, 7]]
------


