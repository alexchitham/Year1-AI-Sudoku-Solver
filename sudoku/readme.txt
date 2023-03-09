Explanation of my approach to the Sudoku Coursework:


I decided to create a depth first, backtracking search with constraint satisfaction. I made this decision as I want to aim for the best marks possible,
and this type of search would likely be the most efficient from the ones taught in the lectures. The constraint satisfaction makes the depth first
search much more efficient, as it stops the algorithm from checking sudoku states that are invalid, so saves a lot of time. I have opted to use recursion 
for the depth first search, rather than iteration, as the code required seems more simple to implement. A local search would not have been appropriate
as we are looking for unique solution, and local searches are only viable really when there are multiple goal states.

An important function within my solution is called possibleVals, this goes through all the empty spaces left in the sudoku board and creates a list
containing all the possible values for each of those empty spaces. This will only be numbers that are valid within the Sudoku game, so the constraints
are used to limit which are the possible numbers. It then orders the empty spaces based on how many valid numbers can be put in them. Then the next
space that the searching algorithm explores is the one with lowest number of possible values. This is the MRV (minimum remaining value) heuristic. The
purpose of using this heuristic is to reduce the branching factor at each stage of the depth-first search. By choosing the node with the fewest children, 
the time to find the unique solution is greatly reduced. 

I tried to add the LCV (least constraining value) heuristic into my solution. As this had the potential to decrease the time of execution yet again. 
However, the way I implemented it actually caused the algorithm to take longer to solve the sudokus, so I decided to remove this feature. Instead of using
a heuristic to sort the values, I just randomised it instead. I do this by using the python Random library. Adding randomness did reduce the time of 
execution slightly. 

The thing I struggled with the most was the optimisation of the code. My code does successfully complete each sudoku given enough time, but some of the
'hard' sudokus take longer than the 20 second limit. Apart from that, the implementation of the algorithm itself was not too difficult. I looked at the
Eight Queens Revisited approach and the Tower of Hanoi to see how their depth first searches worked to get some ideas.

I am reasonably happy with the algorithm I am submitting, but if there was more time, I could have spent it optimising my algorithm, as I will lose marks
from it taking too long to solve. On the hardest puzzle, it takes 380 seconds, but most of the hard ones are around the 30-40 second mark.



