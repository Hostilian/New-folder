Applied Mathematics — Mock Exam 2 (full worked solutions)

Theory
Q1. State complementary slackness conditions and show how they connect primal and dual optimal solutions.
A1. If x is primal feasible and y dual feasible, complementary slackness: for each primal variable x_j, x_j*(A^T y - c)_j = 0; for each dual variable y_i, y_i*(b - A x)_i = 0. These conditions plus feasibility characterize optimality.

Q2. Describe MODI method and when you use it.
A2. MODI (modified distribution) computes potentials (u_i, v_j) for current basic feasible transportation solution and opportunity costs for non-basic cells; if all opportunity costs >=0 the solution is optimal; otherwise adjust along a closed loop.

Q3. Explain EMV and how to compute it on a decision tree.
A3. EMV: assign probabilities to chance nodes, compute expected payoff at each chance node bottom-up, select decision with highest EMV.

Small Example S1
Compute det and invert matrix A=[[1,2],[3,4]]. det = 1*4 - 2*3 = -2. Inverse = (1/det)*[[4,-2],[-3,1]] = -1/2 * [[4,-2],[-3,1]] = [[-2,1],[1.5,-0.5]]

Small Example S2 (simplex pivot)
Starting tableau for Max z=x+y subject to x+2y<=4; x,y>=0. Introduce slack s: x+2y+s=4. Basic var s=4; objective row etc. Perform entering variable y then pivot... (students step through numeric pivot). 

Large Example L1 (LP full)
Max z = 5x + 4y
6x + 4y <= 24
x + 2y <= 6
x,y >=0

Solution L1 (sketch)
Convert to standard form with slacks s1,s2. Initial BFS: s1=24, s2=6. Build tableau and perform simplex iterations. One finds optimal corner after pivots at x=2,y=2 giving z=5*2+4*2=18? Verify: constraints: 6*2+4*2=12+8=20<=24 OK; 2+4=6 OK. Check other corners to ensure optimality.

Large Example L2 (AHP worked)
Given pairwise matrix
   A   B   C
A   1   3   4
B  1/3  1   2
C  1/4 1/2  1
Normalize columns, compute row averages -> priorities.
Column sums: col1 = 1 + 1/3 + 1/4 = 1 + .333 + .25 = 1.583
col2 = 3 + 1 + .5 = 4.5
col3 = 4 + 2 + 1 = 7
Normalized matrix approx: A: [1/1.583, 3/4.5, 4/7] ≈ [0.632, 0.667, 0.571] -> avg ≈ 0.623
Similarly B avg ≈ ... (students compute). Final priority vector (normalized) e.g., [0.62, 0.26, 0.12]

End of Mock 2.
