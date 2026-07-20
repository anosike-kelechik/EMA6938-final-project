# Data

All datasets are loaded programmatically via matminer and do not need to be 
downloaded manually. Raw files over 50 MB are excluded from this repository 
per .gitignore.

Dataset: matbench_mp_gap
- 106,113 inorganic compounds with DFT-computed bandgap values
- Loaded via: from matminer.datasets import load_dataset; load_dataset('matbench_mp_gap')
- Citation: Dunn et al., npj Computational Materials 6, 138 (2020)
- No download required — matminer handles this automatically
