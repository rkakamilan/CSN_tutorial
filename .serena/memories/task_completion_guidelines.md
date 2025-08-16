# Task Completion Guidelines

## What to Do When Tasks Are Completed

Since this is a research/analysis project without traditional development infrastructure, the following guidelines apply:

### 1. Code Validation
- **Manual Testing**: Run modified scripts/notebooks to ensure they execute without errors
- **Data Validation**: Verify output data matches expected formats and ranges
- **Performance Check**: Monitor resource usage and execution time for large calculations

### 2. Documentation Updates
- Update inline comments for any code changes
- Update markdown cells in Jupyter notebooks if modifying analysis
- Ensure README.md reflects any new features or changes

### 3. Data Integrity Checks
```bash
# Verify dataset integrity
wc -l Dataset/glucocorticoid_receptor_2034_2.csv

# Check for expected output files
ls -la *.pickle  # Look for saved computation results

# Validate chemical data processing
python -c "
import pandas as pd
df = pd.read_csv('Dataset/glucocorticoid_receptor_2034_2.csv', sep=';')
print(f'Dataset shape: {df.shape}')
print(f'Missing values: {df.isnull().sum().sum()}')
"
```

### 4. Performance Validation
```bash
# Time script execution
time python Less_Memory_Calculations/CSN_calculations_lessMem.py

# Monitor memory usage during computation
# (Note: This project is designed to be memory-efficient)
```

### 5. Code Quality Checks
- **Syntax Check**: `python -m py_compile script_name.py`
- **Import Validation**: Ensure all required libraries are available
- **Function Testing**: Test individual functions with sample data

### 6. Version Control
```bash
# Stage and commit changes
git add .
git commit -m "Descriptive commit message"

# Check repository status
git status
git log --oneline -5
```

### 7. No Traditional Testing Infrastructure
This project does not have:
- Unit test suites (pytest, unittest)
- Automated linting (flake8, black, etc.)
- Continuous integration pipelines
- Package management files (requirements.txt, setup.py)

### 8. Research Project Specific Checks
- **Reproducibility**: Ensure computations produce consistent results
- **Data Provenance**: Verify dataset sources and licenses remain valid
- **Scientific Accuracy**: Check that algorithmic implementations match literature references
- **Performance Benchmarks**: Compare execution times with published benchmarks

### 9. Final Validation Commands
```bash
# Comprehensive project check
python -c "
import rdkit
import pandas as pd
import numpy as np
import networkx as nx
import matplotlib
print('All core dependencies available')
"

# Verify project structure
find . -name "*.py" -o -name "*.ipynb" | wc -l
find . -name "*.csv" | wc -l
find . -name "*.pickle" | wc -l
```

## Important Notes
- This is primarily a **research/tutorial project**, not a production codebase
- Focus on **computational accuracy** and **reproducibility** rather than software engineering best practices
- **Manual validation** is preferred over automated testing for research computations
- **Documentation** through Jupyter notebook markdown cells is the primary form of project documentation