Applied Mathematics for IT — One-page cheat-sheet (key formulas & steps)

Linear Algebra
- Vector: v = (v1,...,vn). Dot: u·v = sum ui*vi. Norm: ||v|| = sqrt(u·u).
- Matrix multiplication: (AB)ij = sum_k Aik Bkj.
- Gaussian elimination: form upper-triangular -> back-substitution.
- Rank/invertibility: A invertible iff rank(A)=n.

Linear Programming (LP) — Simplex outline
1) Standard form: maximize c^T x subject to Ax = b, x >= 0.
2) Set initial basic feasible solution (introduce slack variables).
3) Build initial tableau, choose entering variable (most negative reduced cost) and leaving variable by min ratio test.
4) Pivot, update tableau. Repeat until no negative reduced costs.
5) Post-optimality: shadow prices = dual variables; reduced costs indicate improvement direction.

Duality (quick)
- Primal (max): max c^T x s.t. Ax <= b, x >= 0. Dual (min): min b^T y s.t. A^T y >= c, y >= 0.
- Weak duality: c^T x <= b^T y. At optimality: equality holds.

Transportation models (steps)
1) Get initial feasible solution: Vogel's Approximation Method (VAM) or Northwest corner.
2) Compute potentials u_i, v_j and opportunity cost for empty cells: cij - (ui+vj).
3) If all opportunities >=0, optimal. Else pivot along closed loop to improve.

Multiple Criteria / AHP (short)
1) Build pairwise comparison matrix A where a_ij = relative importance.
2) Normalize columns and compute priority vector (principal eigenvector or normalized row averages).
3) Check consistency ratio (CR) if needed.

Game Theory (matrix games)
- Pure strategy saddle point when maximin = minimax. For mixed strategies solve linear program or 2x2 closed form.

Decision Analysis (EMV/EOL)
- EMV: expected monetary value = sum(p_i * payoff_i). Choose decision with max EMV.
- EOL: expected opportunity loss.

Exam tips
- Write clean steps: problem setup, method choice, step-by-step pivot/allocations, and interpretation.
- For simplex/tableau show entering/leaving variable and pivot arithmetic.
