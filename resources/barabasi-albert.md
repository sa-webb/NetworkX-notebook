# Barabasi-Albert

Purpose: To model preferential atttachment or how nodes have larger degrees than others.

## Generation Algorithm

Step 1: With a probability p, move to the second step. Else, move to the third step.
Step 2: Connect a new node to existing nodes chosen uniformly at random
Step 3: Connect the new node to n existing nodes with a probability proportional to their degree