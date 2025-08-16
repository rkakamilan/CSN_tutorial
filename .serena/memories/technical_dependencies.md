# Technical Dependencies and Requirements

## Core Dependencies

### Python Libraries (Required)
Based on the codebase analysis, the following libraries are essential:

**Chemical Informatics:**
- `rdkit` - Chemical structure processing, fingerprints, molecular operations
- `rdkit.Chem` - Core molecular chemistry functions
- `rdkit.DataStructs` - Chemical fingerprint operations
- `rdkit.Chem.rdFMCS` - Maximum Common Substructure calculations

**Data Science Stack:**
- `pandas` - DataFrame operations, data manipulation
- `numpy` - Numerical operations, array processing
- `networkx` - Graph/network analysis and visualization

**Visualization:**
- `matplotlib` - Plotting and visualization
- `matplotlib.pyplot` - Standard plotting interface

**Standard Library:**
- `multiprocessing` - Parallel computing for similarity calculations
- `itertools` - Combinatorial operations (combinations)
- `time` - Performance timing
- `os` - System operations (CPU detection)
- `pickle` - Data serialization
- `math` - Mathematical operations (log10)
- `pprint` - Pretty printing for debugging

### System Requirements

**Operating System:**
- Unix-like systems (Linux, macOS) preferred for multiprocessing
- Darwin (macOS) confirmed working environment
- Windows compatibility possible but not verified

**Hardware:**
- **Memory**: Minimum 4GB RAM (tested on Raspberry Pi 400)
- **CPU**: Multi-core recommended for similarity calculations
- **Storage**: Minimal requirements, mainly for dataset and result caching

**Python Version:**
- Python 3.x (specific version not specified in codebase)
- Compatible with modern RDKit versions (2022.03.5+ observed)

## Installation Notes

### RDKit Installation
RDKit requires special installation:
```bash
# Conda (recommended)
conda install -c conda-forge rdkit

# Or via pip (may require additional setup)
pip install rdkit-pypi
```

### Other Dependencies
Most other dependencies can be installed via pip:
```bash
pip install pandas numpy networkx matplotlib
```

## Development Environment

### Jupyter Notebook Environment
- Jupyter Notebook or JupyterLab required for interactive notebooks
- IPython kernel with scientific computing extensions

### IDE Considerations
- Any Python IDE/editor suitable
- Jupyter extension support recommended for notebook development
- Syntax highlighting for chemical SMILES strings helpful

## Performance Considerations

### Multiprocessing Requirements
- Unix-like OS for `os.sched_getaffinity(0)` support
- Multiple CPU cores recommended for MCS calculations
- Memory management important for large datasets

### Optional Performance Tools
- `htop` or similar process monitors
- Memory profiling tools for optimization
- Timing utilities for benchmarking

## Data Dependencies

### ChEMBL Dataset
- Requires access to ChEMBL chemical database
- CSV format with specific column structure expected
- License compliance with Creative Commons Attribution-Share Alike 3.0

### File Formats
- **Input**: CSV (semicolon-separated)
- **Output**: Pickle files for computed results
- **Notebooks**: Jupyter .ipynb format

## No Build System
This project does not use:
- Package managers (requirements.txt, Pipfile, etc.)
- Build systems (setup.py, pyproject.toml)
- Dependency lock files
- Virtual environment specifications

Dependencies are expected to be managed manually or through conda/pip global installations.