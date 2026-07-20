# Phase-Field Informed ML for Microstructure Prediction in Ti-Nb-O Refractory Alloys

**Scientific question:** Can a machine learning model trained on Magpie composition 
descriptors predict bandgap and phase stability properties relevant to interstitial-driven 
microstructure evolution in Ti-Nb-O refractory alloys?

## Dataset
- Source: Materials Project via matminer (`matbench_mp_gap`)
- 106,113 inorganic compounds with DFT-computed bandgap values (GGA-PBE)
- No API key required — loaded automatically via matminer
- Citation: Dunn et al., npj Computational Materials 6, 138 (2020)
- Download: `from matminer.datasets import load_dataset; load_dataset('matbench_mp_gap')`

## Setup Instructions
1. Clone the repository:
   git clone https://github.com/anosike-kelechik/EMA-6938-final-project
   cd EMA-6938-final-project

2. Create the conda environment:
   conda env create -f environment.yml
   conda activate matds

3. If using Materials Project API, copy .env.example to .env and add your key:
   cp .env.example .env

## Running the Notebooks (in order)
1. notebooks/01_data_acquisition.ipynb — loads dataset and saves subset
2. notebooks/02_eda_featurization.ipynb — EDA and Magpie featurization
3. notebooks/03_modeling.ipynb — Random Forest training and evaluation
4. notebooks/04_results_visualization.ipynb — plots and figures

## Key Results
Random Forest on 132 Magpie features achieved MAE = 0.467 eV and R² = 0.771 
for bandgap prediction on 20,000 Materials Project compounds. Prototype-aware 
train/test splitting using crystal system grouping was implemented to assess 
data leakage from structurally similar compounds.

## Repository Structure
EMA-6938-final-project/
├── README.md
├── environment.yml
├── .gitignore
├── .env.example
├── notebooks/
│   ├── 01_data_acquisition.ipynb
│   ├── 02_eda_featurization.ipynb
│   ├── 03_modeling.ipynb
│   └── 04_results_visualization.ipynb
├── data/
│   └── README.md
└── figures/
