# Ex.No: 4   Implementation of Alpha Beta Pruning 
### DATE: 30.08.2025                                                                           
### REGISTER NUMBER : 212223060110
### AIM: 
Write a Alpha beta pruning algorithm to find the optimal value of MAX Player from the given graph.
### Steps:
1. Start the program
2. Initially  assign MAX and MIN value as 1000 and -1000.
3.  Define the minimax function  using alpha beta pruning
4.  If maximum depth is reached then return the score value of leaf node. [depth taken as 3]
5.  In Max player turn, assign the alpha value by finding the maximum value by calling the minmax function recursively.
6.  In Min player turn, assign beta value by finding the minimum value by calling the minmax function recursively.
7.  Specify the score value of leaf nodes and Call the minimax function.
8.  Print the best value of Max player.
9.  Stop the program. 

### Program:

```
import math

# Minimax function
def minimax(curDepth, nodeIndex, maxTurn, scores, targetDepth):
    # Base case: target depth reached
    if curDepth == targetDepth:
        return scores[nodeIndex]

    # If it's the maximizing player's turn
    if maxTurn:
        return max(
            minimax(curDepth + 1, nodeIndex * 2, False, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, False, scores, targetDepth)
        )
    else:
        # If it's the minimizing player's turn
        return min(
            minimax(curDepth + 1, nodeIndex * 2, True, scores, targetDepth),
            minimax(curDepth + 1, nodeIndex * 2 + 1, True, scores, targetDepth)
        )

# Driver code
scores = [3, 5, 2, 9, 12, 5, 23, 20]
treeDepth = int(math.log(len(scores), 2))  # Depth of the game tree

print("The optimal value is:", minimax(0, 0, True, scores, treeDepth))

```













### Output:

<img width="416" height="121" alt="image" src="https://github.com/user-attachments/assets/fd544c4d-558f-44ca-93a1-69a05b1c0fe1" />




### Result:
Thus the best score of max player was found using Alpha Beta Pruning.
