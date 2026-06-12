# Efficient Relaxation for Hamiltonian Engineering

This directory contains notebooks that study an efficient relaxation of the linear program. Instead of using all $3^n$ possible control pulses, a small set of pulses are randomly selected.
## Dependencies

- Python 3.x
- `numpy`, `scipy`, `matplotlib`, `sympy`
- `cvxpy` with the MOSEK solver
- `joblib`, `tqdm` (`eff_relax_plots.ipynb`)
- `quspin` (only in `relaxation_vs_optimal.ipynb` and `tradeoff_graphs.ipynb`)

## Notebooks

| Notebook | Description | Outputs |
| -------- | ----------- | ------- |
| `eff_relax_plots.ipynb` | Probability of obtaining a surjective $F$ as a function of (1) number of modes $n$, (2) root of unity $k$, and (3) number of interaction terms $r$. Each heatmap sweeps the ratio $s/r$ on the $y$-axis. | `eff_relax_modes.pdf`, `eff_relax_root.pdf`, `eff_relax_num_terms.pdf` |
| `relaxation_vs_optimal.ipynb` | Compares the efficient approach with the fully optimal LP  on a 1D chain of length $L = 10$. Plots the gap $\Delta\|\boldsymbol{\lambda}\|_{\ell_1}$ as a function of $s/r$. | `relax_vs_optimal.pdf` |
| `tradeoff_graphs.ipynb` | Scaling of the mean quantum runtime $\langle\|\boldsymbol{\lambda}\|_{\ell_1}\rangle$ with the number of fermionic modes $n$ (10–40) for fixed ratios $s/r \in \{6,7,8,9\}$ on a 1D chain. | `trade_off.pdf` |

