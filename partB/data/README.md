# Dataset Information

## Dataset: Synthetic Random Walk Time Series

### How the dataset is obtained
The dataset is **generated programmatically** using NumPy's random number generator inside the notebooks (`task_2_1.ipynb`). No manual download or external data source is required.

### Generation Method
- A **random walk** is created by taking the cumulative sum of random steps drawn from a standard normal distribution: `T = cumsum(N(0,1))`.
- This is the same synthetic data generation method used in **Section 4.1** of the paper: *"Exact Discovery of Time Series Motifs"* (Mueen et al., KDD 2009).
- The paper states: *"We produced 10 sets of random walks of different sizes containing from 10,000 to 100,000 time series, all of length 1024."*

### Our Configuration (Toy Scale)
- **Database size (m):** 500 time series (scaled down from the paper's 10,000–100,000 for CPU feasibility)
- **Time series length (n):** 128 (scaled down from the paper's 1024 for faster execution)
- **Random seed:** 42 (for full reproducibility)

### Why this dataset is appropriate
- Random walk data is explicitly used by the paper as a scalability benchmark (Section 4.1, Figure 6).
- The paper notes this is actually the **hardest case** for the MK algorithm because no particularly close motif pair is expected.
- It satisfies the Part B requirement of ≥50 consecutive time points and ≥2 continuous numeric features.

### How it is used
- `task_2_1.ipynb`: Dataset generation and exploration
- `task_2_2.ipynb`: MK algorithm reproduction using this dataset
- `task_2_3.ipynb`: Result comparison and reproducibility checklist
- `task_3_1.ipynb`: Ablation studies on this dataset
- `task_3_2.ipynb`: Failure mode analysis (uses a modified variant of this dataset)

### Additional Datasets
- For the **failure mode** (Task 3.2), a separate synthetic dataset with **planted motifs at different amplitudes** is generated inside that notebook to demonstrate the limitations of raw Euclidean distance without Z-normalization.
