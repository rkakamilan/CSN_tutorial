# Suggested Commands for CSN Tutorial Project

## System Information (macOS)
```bash
# System utilities (macOS-specific)
ls -la                    # List files including hidden
find . -name "*.py"       # Find Python files
grep -r "pattern" .       # Search for patterns
which python             # Find Python executable
sw_vers                  # macOS version info
sysctl -n hw.ncpu        # Number of CPU cores
```

## Python Environment
```bash
# Check Python and library versions
python --version
python -c "import rdkit; print(rdkit.__version__)"
python -c "import pandas; print(pandas.__version__)"
python -c "import numpy; print(numpy.__version__)"
python -c "import networkx; print(networkx.__version__)"
python -c "import matplotlib; print(matplotlib.__version__)"
```

## Running the Project

### Jupyter Notebooks (Interactive Analysis)
```bash
# Start Jupyter server
jupyter notebook

# Run specific notebook  
jupyter nbconvert --execute CSN_Jupyter_Notebooks/CSN_glucocorticoid_calculations_2.ipynb

# Convert notebook to script
jupyter nbconvert --to script CSN_Jupyter_Notebooks/CSN_glucocorticoid_calculations_2.ipynb
```

### Python Scripts (Batch Processing)
```bash
# Run memory-efficient calculation script
cd Less_Memory_Calculations
python CSN_calculations_lessMem.py

# Run with timing
time python CSN_calculations_lessMem.py

# Check multiprocessing capabilities
python -c "import multiprocessing; print(f'CPU count: {multiprocessing.cpu_count()}')"
python -c "import os; print(f'Available CPUs: {len(os.sched_getaffinity(0))}')"
```

## Data Analysis Commands
```bash
# Check dataset
head -5 Dataset/glucocorticoid_receptor_2034_2.csv
wc -l Dataset/glucocorticoid_receptor_2034_2.csv

# Monitor running processes
top -pid $(pgrep python)      # Monitor Python processes
ps aux | grep python          # List Python processes
```

## Development Workflow
```bash
# Git operations
git status
git log --oneline -10
git branch
git diff

# Project exploration
find . -name "*.pickle"       # Find saved data files
du -sh *                      # Directory sizes
ls -lh Dataset/               # Check dataset files
```

## Performance Monitoring
```bash
# System monitoring during computation
htop                          # Interactive process viewer (if installed)
iostat 1                      # I/O statistics
vm_stat 1                     # Virtual memory statistics (macOS)
```

## Notes for Darwin/macOS
- Use `brew install` for additional tools if needed
- `os.sched_getaffinity(0)` works on Unix-like systems including macOS
- Memory monitoring: `vm_stat` instead of Linux `free`
- Process monitoring: `ps aux` and `top` work similarly to Linux