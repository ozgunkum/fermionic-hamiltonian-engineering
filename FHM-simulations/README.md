# FHM Simulation Plots

This directory contains notebooks for simulating and analysing Hamiltonian engineering for the 1D spinful Fermionic Hubbard Model (FHM) on a 6-site chain. The notebooks compute exact and engineered time evolution, compare their accuracy, and produce the publication figures.

## Dependencies

- Python 3.x
- `numpy`, `scipy`, `matplotlib`
- `cvxpy` with the MOSEK solver (linear programming for pulse optimisation)
- `h5py` (HDF5 file I/O)

## Notebooks

Run steps 1 and 2 first (in any order); step 3 requires the output of step 2.

| # | Notebook | Description | Inputs | Outputs |
| --- | -------- | ----------- | ------ | ------- |
| 1 | `FHM_1D_HE_energy.ipynb` | Solves the pulse-engineering LP and compares energy expectation value $⟨H_S⟩$ vs. time for exact and engineered (2nd-order Trotter, 2–200 steps) evolution. | Random pulses and target Hamiltonian (internal) | `energy_FHM.pdf` |
| 2 | `FHM_1D_HE_infidelity_statistics.ipynb` | Averages infidelity over 20 independent random samples (random pulses and target Hamiltonians) across 5 simulation times and 10 Trotter step counts. | Random pulses and target Hamiltonians (internal) | `infidelities.hdf5` |
| 3 | `infidelity.ipynb` | Reads the pre-computed infidelities, calculates mean and SEM across the 20 samples, and plots infidelity vs. Trotter steps for each simulation time. | `infidelities.hdf5` | `infidelity_FHM.pdf` |
 
