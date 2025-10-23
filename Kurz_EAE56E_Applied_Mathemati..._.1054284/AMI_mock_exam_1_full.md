Applied Mathematics — Mock Exam 1 (full worked solutions)

Format: 3 theory questions, 2 small examples, 2 large examples. Time suggested: 120 minutes.

Theory
Q1. Explain weak and strong duality for linear programs. (Short answer)
A1. Weak duality: for any primal feasible x and any dual feasible y, c^T x <= b^T y. Strong duality: if both primal and dual have optimal solutions, their objective values are equal and both optima are attained.

Q2. Outline the Vogel's Approximation Method (VAM) for an initial solution of a transportation problem.
A2. Compute row/column penalties = difference between the two smallest costs in each row/column, pick largest penalty, allocate to the cheapest cell in that row/column, reduce supply/demand, repeat until all satisfied.

Q3. Give the main steps to compute priorities in AHP from a 3x3 pairwise comparison matrix.
A3. Normalize columns of the matrix, compute row averages (or compute principal eigenvector) -> priority vector. Optionally compute Consistency Ratio.

Small Example S1 (linear algebra)
Solve by Gaussian elimination: x + 2y - z = 4; 2x - y + 3z = -6; -x + 3y + 2z = 7.

Solution S1
Write augmented matrix (using fractions for exact arithmetic):
\[ \begin{bmatrix}
1 & 2 & -1 & | & 4 \\
2 & -1 & 3 & | & -6 \\
-1 & 3 & 2 & | & 7
\end{bmatrix} \]

Apply row operations (showing exact fractions):
R2 <- R2 - 2·R1:
\[ R2 = [2,-1,3|-6] - 2·[1,2,-1|4] = [0,-5,5|-14]. \]
R3 <- R3 + R1:
\[ R3 = [-1,3,2|7] + [1,2,-1|4] = [0,5,1|11]. \]

Now we have:
\[ \begin{bmatrix}
1 & 2 & -1 & | & 4 \\
0 & -5 & 5 & | & -14 \\
0 & 5 & 1 & | & 11
\end{bmatrix} \]

Eliminate to get an upper triangular form: add R2 to R3 (R3 <- R3 + R2):
\[ R3 = [0,5,1|11] + [0,-5,5|-14] = [0,0,6|-3]. \]
So 6z = -3 => z = -3/6 = -1/2.

Back-substitute into R2:
\[ -5y + 5z = -14 \Rightarrow -5y + 5(-1/2) = -14 \Rightarrow -5y - 5/2 = -14. \]
Multiply both sides by 2 to avoid fractions: -10y - 5 = -28 => -10y = -23 => y = 23/10.

Finally from R1: x + 2y - z = 4
\[ x = 4 - 2y + z = 4 - 2(23/10) + (-1/2) = 4 - 46/10 - 1/2. \]
Compute as fractions: 4 = 40/10, -46/10 gives (40-46)/10 = -6/10, and -1/2 = -5/10 so x = (-6/10 - 5/10) = -11/10.

Exact solution: x = -11/10, y = 23/10, z = -1/2.

Small Example S2 (game theory)
Payoff matrix for Player A (rows) vs B (columns):
    C1  C2
R1   2  -1
R2   0   1
Find whether a pure strategy saddle point exists.

Solution S2
Row minima: R1 -> -1, R2 -> 0. Max of row minima = 0.
Column maxima: C1 -> max(2,0)=2; C2 -> max(-1,1)=1. Min of column maxima = 1.
Since maximin (0) != minimax (1), no saddle point; mixed strategy required.
Remark: If you are asked to compute the mixed strategy for Player A, set probabilities p for R1 and (1-p) for R2 and solve for B's indifference: expected payoff of C1 = 2p + 0(1-p) = 2p; of C2 = -1·p + 1·(1-p) = 1 -2p. Solve 2p = 1 - 2p => p = 1/4. Player A's value = 2p = 1/2.

Large Example L1 (full simplex)
Maximize z = 3x1 + 2x2
Subject to: x1 + x2 <= 4
            2x1 + x2 <= 5
            x1,x2 >=0

Solution L1 (graphical / simplex)
We can examine corner points (or run simplex):
- (0,0): z = 0
- (0,4): z = 2*4 = 8  (2nd constraint: 2·0+4 = 4 ≤ 5 OK)
- (2.5,0): satisfies 2·2.5 + 0 = 5 ≤ 5, z = 3·2.5 = 7.5
- Intersection of the two constraints: solve
    x1 + x2 = 4
 2x1 + x2 = 5
Subtract: x1 = 1, then x2 = 3 => z = 3·1 + 2·3 = 9.

Thus the optimum is at (x1,x2) = (1,3) with z* = 9.

Large Example L2 (transportation) — small solved allocation
Supplies: S1=20, S2=30. Demands: D1=15, D2=35. Costs:
      D1  D2
S1    8   6
S2    4   7

Solution L2 (use Vogel initial + adjust by inspection — for variety we'll show a feasible optimal solution and its cost)
Total supply 50 equals demand 50.
Vogel penalties initial: Row1 penalty = |6-8|=2; Row2 penalty=|4-7|=3; Col1 penalty = |4-8|=4; Col2 penalty = |7-6|=1. Highest penalty column1 -> choose minimal cost in col1 is 4 at S2-D1. Allocate min(S2=30,D1=15) -> allocate 15 to S2-D1. Now S2 remaining 15; D1 satisfied.
Remaining demands: D2=35, supplies S1=20, S2=15.
Next penalties quickly lead to allocating S1-D2=20, S2-D2=15. So allocations:
S1->D2:20 at cost 6 -> 120
S2->D1:15 at cost 4 -> 60
S2->D2:15 at cost 7 -> 105
Total cost = 285.
Check optimality (outline of MODI): label basic cells and compute potentials u_i, v_j so that u_i + v_j = c_ij for each occupied cell; compute opportunity costs for empty cells as c_ij - (u_i+v_j). If all opportunity costs >= 0 the solution is optimal. For this allocation one can verify there are no negative opportunity costs (I can show the full MODI table if you want).

End of Mock 1.

Sources used
- `extracted/plain/SQ10.md` (Game Theory study questions)
- `extracted/plain/SQ11.md` (Decision models study questions)
- `extracted/plain/SQ12.md` (Multiple criteria / other study questions)
- `extracted/plain/Seminar9_-_Routing_problem__distribution__salesman___.md`
- `extracted/plain/Seminar_10-MADM.md`
- `extracted/plain/Seminar_12_-_Decision_Models.md`
