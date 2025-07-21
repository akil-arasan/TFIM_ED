# 🧊 1D Transverse Field Ising Model (TFIM) Simulation

This project performs **exact diagonalization** of the **Transverse Field Ising Model (TFIM)** — a key model in quantum many-body physics and quantum computing. The goal is to compute the **ground state energy** for 1D spin chains of various lengths and transverse field strengths.

---

## 🔬 Model

The TFIM Hamiltonian is given by:

$$
H = -J \sum_{i=1}^{N} \sigma^z_i \sigma^z_{i+1} - h \sum_{i=1}^{N} \sigma^x_i
$$

Where:
- $\( \sigma^z \) and \( \sigma^x \)$ are Pauli matrices
- $\( J \)$ is the interaction strength (set to 1 by default)
- $\( h \)$ is the transverse field strength
- Periodic boundary conditions (PBC) is not used

---

## 🚀 Features

- Exact diagonalization using `scipy.linalg.eigh` for small systems (for N less then 13)
- Optional use of sparse methods (`scipy.sparse.linalg.eigsh`) for larger systems (for N greater then 12)
- Compute:
  - Ground state energy $\( E_0 \)$
- Parameter sweep over system size $\( N \)$ and field strength $\( h \)$
- Progress bar using `tqdm`
- Results saved as a pivoted `.csv` table (rows = $\( N \)$, columns = $\( h \)$, values = $\( E_0 \)$)

---

## 📁 Output

- `tfim_ED_results.csv`: pivot table of ground state energies
- `results_raw.csv` (optional): raw data with columns `["N", "h", "E0", "Gap"]`
- (Optional) Formatted Python lists for further analysis or plotting

---

## 📦 Requirements

- Python 3.7+
- NumPy
- SciPy
- Pandas
- tqdm

Install them using:

```bash
pip install numpy scipy pandas tqdm
