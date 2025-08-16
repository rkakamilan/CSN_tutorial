# Code Style and Conventions

## Programming Language
- **Python** - All code is written in Python

## Code Structure and Style
Based on analysis of the codebase, the following conventions are observed:

### Import Organization
```python
# Standard library imports
from time import time
import os
import multiprocessing

# Scientific computing libraries  
import numpy as np
import pandas as pd

# Domain-specific libraries (RDKit, NetworkX)
from rdkit import Chem
from rdkit import rdBase
import networkx as nx

# Visualization
import matplotlib as mpl
import matplotlib.pyplot as plt
```

### Variable Naming
- **snake_case** for variables and functions: `start_time`, `num_cpus`, `mol_tuples`
- **Descriptive names**: `chembl_ids`, `rdkit_can_smiles`, `tan_similarity`
- **DataFrame variables**: `df`, `df1`, `df2`, etc. for progressive transformations

### Function Definitions
- Functions use descriptive names: `tc_mcs()`, `minuslog()`
- Clear parameter names: `mol1`, `mol2`, `key`
- Type hints are not used in this codebase

### Comments and Documentation
- **Inline comments** for code explanations (Japanese preference per CLAUDE.md)
- **Section headers** using markdown-style comments in notebooks
- **Docstrings** not extensively used but would be in English when present
- **Process documentation** through markdown cells in Jupyter notebooks

### Data Handling Patterns
- **pandas operations**: Extensive use of DataFrame operations, groupby, indexing
- **RDKit integration**: Converting SMILES to mol objects, fingerprint calculations
- **Dictionary-based data structures**: `node_data`, `subsets` for complex nested data

### Multiprocessing Patterns
```python
# Standard multiprocessing pattern used
if __name__ == '__main__':
    with Pool(num_cpus) as p:
        star_map = p.starmap(function_name, data_tuples)
```

### Error Handling
- Minimal explicit error handling observed
- Relies on library defaults and timeouts (e.g., `timeout=10` in FindMCS)

### Performance Considerations
- Memory-efficient alternatives provided (`CSN_calculations_lessMem.py`)
- CPU usage optimization with `num_cpus = len(os.sched_getaffinity(0)) - 2`
- Progress tracking through print statements in loops

## File Organization
- **Jupyter Notebooks**: Interactive analysis and visualization
- **Python Scripts**: Production/batch processing versions
- **Clear separation**: Original vs memory-optimized versions