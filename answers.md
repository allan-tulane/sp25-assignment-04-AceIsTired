# CMPS 2200 Assignment 5
## Answers

**Name:** Jamari Ross






- **1a.**
  The maximum depth is $O(\log_d n)$.

- **1b.**
  The work done in the insert operation is $O(\log_d n)$ because only one swap is done at each level.
  The work done in delete is $O(d \log_d n)$ because there are d comparisons made to find the minimum amount of childeren, and a possible swap.

- **1c.**
  $O(d|V|\log_d|V| + |E|\log_d|V|)$ where the first term represents the mimimun work of the delete operation, and the second term is the work of the insert operation.
  
- **1d.**
  $O(|E|/|V|)$ gives us the running time we want to achieve.

- **2a.**
  APSP(i, j, 0):
    APSP(0,0,0) = 0
    APSP(0,1,0) = -2
    APSP(0,2,0) = 2
    APSP(1,0,0) = ∞
    APSP(1,1,0) = 0
    APSP(1,2,0) = 0
    APSP(2,0,0) = 0
    APSP(2,1,0) = 0
    APSP(2,2,0) = 0

  APSP(i, j, 1):
    APSP(0,0,1) = 0
    APSP(0,1,1) = -2
    APSP(0,2,1) = -1
    APSP(1,0,1) = ∞
    APSP(1,1,1) = 0
    APSP(1,2,1) = 1
    APSP(2,0,1) = ∞
    APSP(2,1,1) = ∞
    APSP(2,2,1) = 0

  APSP(i, j, 2):
    APSP(0,0,2) = 0
    APSP(0,1,2) = -2
    APSP(0,2,2) = -1
    APSP(1,0,2) = ∞
    APSP(1,1,2) = 0
    APSP(1,2,2) = 1
    APSP(2,0,2) = ∞
    APSP(2,1,2) = ∞
    APSP(2,2,2) = 0

- **2b.**
  APSP(i,j,2) = min(APSP(i,j,1), APSP(i,2,1) + APSP(2,j,1))

- **2c.**
  The shortest path from i to j through the required verticies either doesnt pass through k (so best path stays the same), or does pass through k, which would make the cost the sum of i -> k and j -> k.
  Therefore, the optimal substructure would be:
    APSP(i,j,k) = min(APSP(i,j,k-1), APSP(i,k,k-1) + APSP(k,j,k-1))
  
- **2d.**
  The number of distinct subproblems is $n^3$ and the work is $O(n^3)$.

- **2e.**
  Our dynamic programing method is better suited for smaller and dense graphs.

- **3a.**
  Yes, because minimizes the total weight as well as heavy edges (when needed), making the maximum edge weight minimized as well.

- **3b.**
  First find the MST, then iterate through each edge not in the MST, delete the largest/heaviest edge and continue until all points have been iterated through.Track the weights of the creaated trees and pick the one that has the least weight and is still larger      than the initial MST weight.

- **3c.**
  $O(E log E)$ is the work for the algorithm.
