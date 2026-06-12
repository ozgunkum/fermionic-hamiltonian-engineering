# 1088-Mode Harper-Hofstadter Simulation Plots

This directory contains notebooks for simulating and analysing Hamiltonian engineering on a 32×34 square lattice (1088 fermionic modes) targeting the Harper-Hofstadter model. The notebooks compute Slater matrix time evolution, compare engineered versus exact dynamics, and produce the publication figures.

## Dependencies

- Python 3.x
- `numpy`, `scipy`, `matplotlib`
- `cvxpy` (linear programming for pulse optimisation)
- `h5py` (HDF5 file I/O)

## Notebooks

Run step 1 first; steps 2–4 can then be run in any order. Step 5 is independent of all others.

| # | Notebook | Description | Inputs | Outputs |
| --- | -------- | ----------- | ------ | ------- |
| 1 | `1088_slater_matrices.ipynb` | Solves the pulse-engineering LP (via CVXPY), then runs both exact diagonalisation (1000 steps, $t \in [0, 80]$) and engineered time evolution (10 Trotter-step levels, sampled at 7 times). **Computationally intensive — expect several hours on a workstation.** | Hamiltonian parameters  | `slater_matrices_1088.hdf5` |
| 2 | `1088_bond_currents.ipynb` | Computes edge currents (left/right/top/bottom) from the reduced density matrices and plots engineered vs. exact comparison with error bars. | `slater_matrices_1088.hdf5` | `edge_currents.pdf` |
| 3 | `1088_energy.ipynb` | Evaluates the Hamiltonian energy expectation value over time and plots the relative error between engineered and exact evolutions. | `slater_matrices_1088.hdf5` | `energy_HH.pdf` |
| 4 | `1088_infidelity.ipynb` | Computes state infidelity ($1 - \lvert\det(\Phi^\dagger_\text{exact}\,\Phi_\text{eng})\rvert^2$) between engineered and exact evolution as a function of Trotter step count. | `slater_matrices_1088.hdf5` | `infidelity_HH.pdf` |
| 5 | `average_quantum_runtime.ipynb` | Runs 100 random pulse-sampling trials to estimate the mean quantum runtime required to satisfy the engineering constraints. Independent of all other notebooks. | Hamiltonian parameters  | `quantum_runtimes.hdf5` |
