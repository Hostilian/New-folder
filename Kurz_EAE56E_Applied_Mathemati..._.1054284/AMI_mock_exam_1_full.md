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
Write augmented matrix:
[ [1,2,-1 | 4], [2,-1,3 | -6], [-1,3,2 | 7] ]
R2 <- R2 - 2*R1 -> [0, -5, 5 | -14]
R3 <- R3 + R1 -> [0, 5, 1 | 11]
Now R3 <- R3 + R2 -> [0,0,6 | -3]
So z = -3/6 = -1/2.
Back-substitute into R2: -5y + 5z = -14 -> -5y + 5*(-1/2) = -14 -> -5y - 2.5 = -14 -> -5y = -11.5 -> y = 2.3
Then x from R1: x + 2*2.3 - (-0.5) = 4 -> x + 4.6 + 0.5 = 4 -> x + 5.1 = 4 -> x = -1.1
(Numeric fractions: y = 23/10, z = -1/2, x = -11/10.)

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

Large Example L1 (full simplex)
Maximize z = 3x1 + 2x2
Subject to: x1 + x2 <= 4
            2x1 + x2 <= 5
            x1,x2 >=0

Solution L1 (graphical / simplex)
We can examine corner points: (0,0): z=0. (0,4): z=8 (but check second constraint: 2*0 +4 =4 <=5 OK). Intersection of constraints: solve x1+x2=4 and 2x1+x2=5 -> subtract gives x1=1, x2=3 -> z=3*1+2*3=9. Point (2.5,0) doesn't satisfy second constraint: 2*2.5 +0 =5 OK -> x1=2.5,x2=0 yields z=7.5. So best among feasible corners is (1,3) with z=9.

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
Check optimality (MODI) would compute potentials; for this small example students should run MODI to verify no negative opportunity costs. (Detailed MODI arithmetic omitted here but can be supplied on request.)

End of Mock 1.
