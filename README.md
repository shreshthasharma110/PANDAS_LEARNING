# 📊 PANDAS_LEARNING  
**A hands‑on, notebook‑driven guide to mastering Pandas for data analysis**  

[![GitHub license](https://img.shields.io/github/license/shreshthasharma110/PANDAS_LEARNING)](LICENSE)  
[![GitHub stars](https://img.shields.io/github/stars/shreshthasharma110/PANDAS_LEARNING?style=flat)](https://github.com/shreshthasharma110/PANDAS_LEARNING/stargazers)  
[![GitHub forks](https://img.shields.io/github/forks/shreshthasharma110/PANDAS_LEARNING?style=flat)](https://github.com/shreshthasharma110/PANDAS_LEARNING/network)  
[![Python version](https://img.shields.io/badge/python-3.9%2B-blue)](https://www.python.org/downloads/)  

> **Quick links** – [Demo notebooks (nbviewer)](https://nbviewer.org/github/shreshthasharma110/PANDAS_LEARNING/tree/main/) • [Issues](https://github.com/shreshthasharma110/PANDAS_LEARNING/issues) • [Pull Requests](https://github.com/shreshthasharma110/PANDAS_LEARNING/pulls)

---

## Overview
`PANDAS_LEARNING` is a curated collection of Jupyter notebooks that walk you through the core concepts of the **Pandas** library—from basic `Series` objects to advanced data‑cleaning techniques. It is designed for:

* **Beginners** who want a practical, code‑first introduction.  
* **Data‑science students** looking for concise, runnable examples.  
* **Professionals** needing a quick refresher on common Pandas workflows.

All notebooks are self‑contained, include explanatory markdown cells, and can be executed in any standard Python environment.

**Current version:** `v1.0.0` (July 2026)  

---

## Features
| Feature | Description | Status |
|---------|-------------|--------|
| **Series fundamentals** | Creation, indexing, vectorized operations, and basic statistics. | ✅ Stable |
| **DataFrame basics** | Building DataFrames, column/row selection, and descriptive stats. | ✅ Stable |
| **Data loading** | Reading CSV, Excel, JSON, and SQL sources with `read_*` functions. | ✅ Stable |
| **Data cleaning** | Handling missing values, duplicates, type conversion, and outlier detection. | ✅ Stable |
| **Filtering & sorting** | Boolean indexing, `query()`, multi‑column sorting, and `groupby` basics. | ✅ Stable |
| **Visualization hooks** | Quick integration with Matplotlib/Seaborn for exploratory plots. | 🟡 Beta |
| **Performance tips** | Using `categorical` dtype, chunked reading, and `eval/numexpr`. | 🟡 Beta |

---

## Tech Stack
| Layer | Technology | Reason |
|-------|------------|--------|
| **Language** | Python 3.9+ | Modern, widely adopted for data science. |
| **Core library** | Pandas 2.x | Powerful data manipulation & analysis. |
| **Notebook engine** | Jupyter Notebook (or JupyterLab) | Interactive, cell‑based execution. |
| **Supporting libs** | NumPy, Matplotlib, Seaborn | Numerical operations & quick visual checks. |
| **Package manager** | pip (or conda) | Simple installation across platforms. |

---

## Architecture
The repository follows a flat, notebook‑centric layout:

```
PANDAS_LEARNING/
├── 01_series.ipynb          # Series creation & operations
├── 02_dataframe.ipynb       # DataFrame fundamentals
├── 03_data_loading.ipynb    # Importing data from various sources
├── 04_data_cleaning.ipynb   # Cleaning & preprocessing techniques
├── 05_filtering_sorting.ipynb # Filtering, sorting, grouping
└── README.md                # This documentation
```

Each notebook is independent but builds on concepts introduced earlier, allowing linear progression or selective study.

---

## Getting Started

### Prerequisites
| Tool | Minimum version |
|------|-----------------|
| Python | 3.9 |
| pip (or conda) | latest |
| Git | 2.20+ (optional, for cloning) |
| Jupyter | 1.0+ |

> **Note:** If you prefer an isolated environment, we recommend using `venv` or `conda`.

### Installation

```bash
# 1️⃣ Clone the repository
git clone https://github.com/shreshthasharma110/PANDAS_LEARNING.git
cd PANDAS_LEARNING

# 2️⃣ Create a virtual environment (optional but recommended)
python -m venv .venv
# On Windows
.\.venv\Scripts\activate
# On macOS/Linux
source .venv/bin/activate

# 3️⃣ Install dependencies
pip install --upgrade pip
pip install pandas jupyter matplotlib seaborn
```

> **Alternative (conda)**  
> ```bash
> conda create -n pandas_learning python=3.11 pandas jupyter matplotlib seaborn -y
> conda activate pandas_learning
> ```

### Verification
```bash
# Launch Jupyter and ensure the kernel starts without errors
jupyter notebook
```
Your default web browser should open the Jupyter dashboard. Click any `*.ipynb` file to start exploring.

---

## Usage

### Running a notebook
1. From the Jupyter dashboard, click on the notebook you wish to explore (e.g., `01_series.ipynb`).  
2. Execute cells sequentially using **Shift + Enter**.  
3. Modify code blocks to experiment with your own data.

### Example: Creating a Series
```python
import pandas as pd

# Simple numeric series
s = pd.Series([10, 20, 30, 40], index=['a', 'b', 'c', 'd'])
print(s)
```
**Expected output**
```
a    10
b    20
c    30
d    40
dtype: int64
```

### Common workflows
| Goal | Notebook | Code snippet |
|------|----------|--------------|
| Load a CSV file | `03_data_loading.ipynb` | `df = pd.read_csv('data.csv')` |
| Drop rows with missing values | `04_data_cleaning.ipynb` | `df_clean = df.dropna()` |
| Filter rows where `age > 30` | `05_filtering_sorting.ipynb` | `df_filtered = df.query('age > 30')` |
| Group by `category` and compute mean | `05_filtering_sorting.ipynb` | `df.groupby('category').mean()` |

---

## Development

If you want to contribute new notebooks, improve existing ones, or add tests:

1. **Fork** the repository.  
2. Create a feature branch: `git checkout -b feature/add-time-series`.  
3. Install the **dev** extras (optional):  
   ```bash
   pip install -e .[dev]   # Requires a `setup.cfg`/`pyproject.toml` – add if you expand the repo.
   ```
4. Run the notebooks locally to ensure they execute without errors.  
5. Commit with clear messages and push to your fork.  
6. Open a **Pull Request** targeting `main`.

### Code style
* Follow **PEP 8** (use `black` or `ruff` for auto‑formatting).  
* Keep notebook cells short and focused; add markdown explanations.  

### Testing (future)
We plan to add unit tests using `pytest` and `nbval` to validate notebook execution. Contributions that include tests are highly welcomed.

---

## Deployment

The notebooks are intended for local, interactive use. However, you can:

* **Publish** them as static HTML via `nbconvert`:
  ```bash
  jupyter nbconvert --to html 01_series.ipynb
  ```
* **Host** on GitHub Pages using the `nbviewer` link (already provided in the Quick links).  
* **Dockerize** for reproducible environments (example Dockerfile below):

```dockerfile
# Dockerfile (optional)
FROM python:3.11-slim

RUN pip install --no-cache-dir pandas jupyter matplotlib seaborn

WORKDIR /app
COPY . /app

EXPOSE 8888
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--no-browser", "--allow-root"]
```

Build & run:
```bash
docker build -t pandas_learning .
docker run -p 8888:8888 pandas_learning
```

---

## API Documentation
*This repository does **not** expose a public API.*  
All interactions are performed through the Pandas library inside the notebooks.

---

## Contributing

We welcome contributions of any size—new notebooks, corrections, visual enhancements, or documentation updates.

1. **Read** the [Code of Conduct](CODE_OF_CONDUCT.md) (if added).  
2. **Fork** the project and create a feature branch.  
3. **Make** your changes, ensuring all cells run from top to bottom without errors.  
4. **Write** a concise PR description and reference any related issues.  
5. **Submit** the PR; maintainers will review and merge.

### Helpful resources
* Pandas official docs – https://pandas.pydata.org/docs/  
* Jupyter Notebook docs – https://jupyter.org/documentation  

---

## Troubleshooting & FAQ

| Problem | Solution |
|---------|----------|
| `ModuleNotFoundError: No module named 'pandas'` | Ensure you installed dependencies in the active environment (`pip install pandas`). |
| Notebook won’t start (`Kernel died`) | Verify you are using a supported Python version (≥ 3.9) and that `jupyter` is installed. |
| Data files not found | Notebooks use placeholder paths; replace with absolute/relative paths to your own data. |
| Plot not displaying | Run `%matplotlib inline` at the top of the notebook or enable the JupyterLab renderer. |

If you can’t find an answer, open an **issue** with a minimal reproducible example.

---

## Roadmap

| Milestone | Target date | Description |
|-----------|-------------|-------------|
| **v1.1** | Aug 2026 | Add notebooks on time‑series analysis & window functions. |
| **v1.2** | Oct 2026 | Introduce `pandas‑flavor` for custom accessor examples. |
| **v2.0** | Jan 2027 | Full test suite with `nbval`; Docker images published to Docker Hub. |
| **Community** | Ongoing | Collect community‑submitted notebooks via PRs. |

---

## License & Credits

**License:** MIT License – see the [LICENSE](LICENSE) file for details.  

**Author:** Shreshtha Sharma ([@shreshthasharma110](https://github.com/shreshthasharma110))  

**Contributors:**  
* List of contributors is automatically generated by GitHub.  

**Acknowledgments:**  
* The Pandas development team for the powerful library.  
* Jupyter community for the interactive notebook platform.  

--- 

*Happy data wrangling!* 🚀