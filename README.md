# KenKen is a puzzle published in *The New York Times* on Sundays. 

The puzzle is similar to Sudoku: it's a square grid of numbers (5x5 or 7x7) which must be filled in so that each digit appears only once in each row and column. Instead of smaller square sections within the grid that must also contain unique numbers (as in Sudoku), in KenKen, the grid is subdivided into heavily outlined sections of varying size and geometry, and the solver must use arithmetic to correctly fill them. The clues consist of a number -- a sum, difference, product, or quotient -- and the operation (+, -, x, or /) required to make the digits within the section yield that number. 

This project originated when I decided to write my own KenKen puzzle. I was able to construct a 7x7 grid without digits repeated in the rows or columns: the answer. But when it came to outlining the different sections and writing the clues, I realized I needed information on what made a clue easy or difficult. Otherwise the puzzle might turn out unsolvable or not fun.

## The goal:
My goal was to analyze all the possible combinations of two, three, and four numbers that could occur within a heavily outlined section of a KenKen puzzle and create a reference tool that would allow a puzzle constructor to choose an appropriate mix of easy and difficult clues and combinations of numbers. What makes a KenKen clue difficult is the number of possible solutions: for example, in a 7x7 puzzle, a section of three squares clued "18x" (let's assume the squares are in a straight line, indicating numbers must be unique) can contain only one possible combination of three numbers (6,3,1), whereas the same section clued "10+" has four possible solutions ([6,3,1], [7,2,1], [5,4,1], [5,2,3]), making the latter a more difficult clue. 

Some rules seemed apparent from my experience solving these puzzles: for instance, two-square sections are generally easier to solve than larger sections (fewer possible combinations); 3- and 4- square sections are generally more difficult when their squares are not in a straight line (because the repetition of numbers is possible in this configuration); and the possible clues for certain pairs of numbers skew easier than those for other pairs -- e.g. three of the four possible clues for (7,1) are extremely easy (that pair is the only possible solution for "6-", "7/", and "7*"; the other possible clue, "8+", has three possible solutions, whereas none of the three possible clues for the pair (3,2) ("5+",  "6*", "1-") is an "easy" single-solution clue. I wanted to codify these rules by creating a reference that allows a constructor to compare the difficulty of their cluing options at a glance.

## Method:

## Constraints:
This project does not consider the geometry of a section when identifying possible combinations of numbers. For example, the combinations of four numbers allow for repetition of up to two pairs, which is only possible in a square configuration (a single pair of duplicate numbers would be possible in a 4-square section with three squares along one axis and one square perpendicular). Constructors will have to eliminate those possibilities where appropriate when they use this tool. 

This project also considers four to be the maximum number of squares in a section. I have never seen a puzzle that contains a larger section, although I don't know if that rule is written anywhere. 

## Other uses:
Of course, this tool is also useful for solvers of KenKen! 

