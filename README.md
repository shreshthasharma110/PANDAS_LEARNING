# 📊 Pandas Learning Guide  
**Hands-on Jupyter notebooks for mastering Pandas data analysis**  

[![GitHub license](https://img.shields.io/github/license/shreshthasharma110/PANDAS_LEARNING)](LICENSE)  
[![GitHub stars](https://img.shields.io/github/stars/shreshthasharma110/PANDAS_LEARNING?style=flat)](https://github.com/shreshthasharma110/PANDAS_LEARNING/stargazers)  
[![Python version](https://img.shields.io/badge/python-3.9%2B-blue)](https://www.python.org/downloads/)  

> **Quick links** – [Demo notebooks](https://nbviewer.org/github/shreshthasharma110/PANDAS_LEARNING/tree/main/) • [Issues](https://github.com/shreshthasharma110/PANDAS_LEARNING/issues) • [Pull Requests](https://github.com/shreshthasharma110/PANDAS_LEARNING/pulls)

---

## Overview  
Pandas Learning is a curated set of Jupyter notebooks for mastering **Pandas** (v2.x) through practical examples. Designed for:

- **Beginners**: Code-first introduction to Series/DataFrames  
- **Data scientists**: Concise examples of common workflows  
- **Professionals**: Quick refresher on core Pandas operations  

All notebooks are self-contained with markdown explanations and executable code.  

**Current version:** v1.0.0 (July 2026)  

---

## Core Features  
| Feature | Status |
|---------|--------|
| Series creation & operations | ✅ Stable |
| DataFrame fundamentals (selection, stats) | ✅ Stable |
| Data loading (CSV, Excel, SQL) | ✅ Stable |
| Data cleaning (missing values, outliers) | ✅ Stable |
| Filtering & sorting (boolean indexing, `groupby`) | ✅ Stable |
| Visualization integration (Matplotlib/Seaborn) | 🟡 Beta |
| Performance optimization (categorical dtype) | 🟡 Beta |

---

## Tech Stack  
- **Language**: Python 3.9+  
- **Core**: Pandas 2.x  
- **Notebooks**: Jupyter Notebook/Lab  
- **Supporting**: NumPy, Matplotlib, Seaborn  
- **Environment**: pip/conda  

---

## File Structure  
```
PANDAS_LEARNING/
├── 01_series.ipynb          # Series fundamentals  
├── 02_dataframe.ipynb       # DataFrame basics  
├── 03_data_loading.ipynb    # CSV/Excel/SQL loading  
├── 04_data_cleaning.ipynb   # Cleaning techniques  
├── 05_filtering_sorting.ipynb # Filtering & grouping  
└── README.md                # This documentation  
```

---

## Getting Started  

### Requirements  
| Tool | Minimum Version |
|------|-----------------|
| Python | 3.9+ |
| Jupyter | 1.0+ |
| Git (optional) | 2.20+ |

### Installation  
```bash
# Clone repository
git clone https://github.com/shreshthasharma110/PANDAS_LEARNING.git
cd PANDAS_LEARNING

# Create virtual environment (optional)
python -m venv .venv
source .venv/bin/activate  # or .\.venv\Scripts\activate on Windows

# Install dependencies
pip install pandas jupyter matplotlib seaborn
```

### Launch Jupyter  
```bash
jupyter notebook
```
Open any `.ipynb` file in your browser to start.

---

## Usage Examples  

### Basic Series Creation  
```python
import pandas as pd

s = pd.Series([10, 20, 30], index=['a', 'b', 'c'])
print(s)
```
**Output:**  
```
a    10
b    20
c    30
dtype: int64
```

### Common Workflows  
| Task | Notebook | Code |
|------|----------|------|
| Load CSV | `03_data_loading.ipynb` | `pd.read_csv('data.csv')` |
| Clean missing values | `04_data_cleaning.ipynb` | `df.dropna()` |
| Filter rows | `05_filtering_sorting.ipynb` | `df.query('age > 30')` |

---

## Development  

### Contribution Workflow  
1. Fork the repo  
2. Create a feature branch  
3. Install dev tools (optional):  
   ```bash
   pip install -e .[dev]  # Requires setup.cfg
   ```
4. Test notebooks locally  
5. Submit PR with clear changelog  

### Style Guidelines  
- Follow [PEP 8](https://peps.python.org/pep-0008/)  
- Use `black` or `ruff` for formatting  
- Keep notebook cells focused with markdown explanations  

---

## Deployment Options  

### Export to HTML  
```bash
jupyter nbconvert --to html 01_series.ipynb
```

### Docker Setup (optional)  
```Dockerfile
FROM python:3.11-slim
RUN pip install pandas jupyter matplotlib
WORKDIR /app
EXPOSE 8888
CMD ["jupyter", "notebook", "--ip=0.0.0.0"]
```

---

## Contributing  
All contributions welcome!  

1. Read [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md)  
2. Fork and create a feature branch  
3. Ensure all notebook cells execute without errors  
4. Submit PR with clear description  

**Resources:**  
- [Pandas docs](https://pandas.pydata.org/docs/)  
- [Jupyter docs](https://jupyter.org/documentation)  

---

## Roadmap  
| Milestone | Target Date | Description |
|-----------|-------------|-------------|
| v1.1 | Aug 2026 | Time-series analysis notebooks |
| v1.2 | Oct 2026 | Custom accessor examples |
| v2.0 | Jan 2027 | Full test suite with `nbval` |

---

## License & Credits  
**License:** MIT – see [LICENSE](LICENSE)  

**Author:** Shreshtha Sharma ([@shreshthasharma110](https://github.com/shreshthasharma110))  

**Acknowledgments:**  
- Pandas development team  
- Jupyter community  

--- 

*Happy data wrangling!* 🚀