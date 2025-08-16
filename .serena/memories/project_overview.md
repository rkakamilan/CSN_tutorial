# CSN Tutorial Project Overview

## Project Purpose
This repository contains Supporting Information code for a research paper on visualizing chemical space networks with RDKit and NetworkX. The paper is:

Scalfani, V.F., Patel, V.D. & Fernandez, A.M. Visualizing chemical space networks with RDKit and NetworkX. *J Cheminform*, **2022**, *14*, 87. https://doi.org/10.1186/s13321-022-00664-x

The project demonstrates how to:
1. Process ChEMBL chemical datasets 
2. Calculate molecular similarity metrics (Tanimoto similarity, MCS-based similarity)
3. Create chemical space networks for visualization and analysis
4. Handle memory-efficient calculations for large datasets

## Tech Stack
- **Python** - Primary programming language
- **RDKit** - Chemical informatics library for molecular operations
- **NetworkX** - Network analysis and graph operations
- **pandas** - Data manipulation and analysis
- **NumPy** - Numerical computations
- **matplotlib** - Data visualization
- **multiprocessing** - Parallel computing for similarity calculations
- **Jupyter Notebooks** - Interactive development and analysis

## Project Structure
```
CSN_tutorial/
├── CSN_Jupyter_Notebooks/          # Original manuscript notebooks
│   ├── CSN_glucocorticoid_calculations_2.ipynb
│   ├── CSN_glucocorticoid_tan_sim_2.ipynb
│   └── CSN_glucocorticoid_MCS_2.ipynb
├── Dataset/                         # ChEMBL dataset and license
│   ├── glucocorticoid_receptor_2034_2.csv
│   └── dataset_license
├── Less_Memory_Calculations/        # Memory-efficient alternative
│   └── CSN_calculations_lessMem.py
├── README.md
└── LICENSE
```

## Key Features
- Chemical similarity calculations using RDKit fingerprints
- Maximum Common Substructure (MCS) based Tanimoto coefficients  
- Multiprocessing support for performance optimization
- Memory-efficient algorithms for resource-constrained environments
- Benchmark data showing performance on different hardware configurations

## Target Hardware Performance
The project includes benchmark data for `CSN_calculations_lessMem.py`:
- 12th generation Intel Core i9, 64 GB RAM (22 cores): ~25 min
- Raspberry Pi 5, 8 GB RAM (3 cores): ~3 hours  
- Raspberry Pi 400, 4 GB RAM (3 cores): ~5 hours

## Research Context
This is a chemoinformatics research project focusing on computational chemistry, molecular similarity analysis, and chemical space visualization techniques.