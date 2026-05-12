# Machine Learning Project: Wine Quality Prediction
**Course**: Machine Learning (6 SIN-A)  
**Institution**: Universidad Internacional del Ecuador  
**Team Members**: Andrés Quisilema & José Quishpe  
**Date**: 10 Mayo 2026

---

## Project Overview

This project implements both **Linear Regression** and **Logistic Regression** models to predict wine quality based on physicochemical properties, demonstrating a complete machine learning pipeline with reproducible tooling.

---

## Dataset
**Wine Quality Dataset** (UCI Machine Learning Repository)
- **Source**: [UCI Wine Quality](https://archive.ics.uci.edu/dataset/186/wine+quality)
- **Samples**: 1,599 red wines
- **Features**: 11 physicochemical properties
- **Targets**:
  - **Regression**: `quality` score (3-8 scale)
  - **Classification**: Good wine (quality ≥ 7) vs Bad wine (quality < 7)

---

## Technology Stack

### Data Wrangling: **Polars 1.8.x**
We selected **Polars** over traditional frameworks due to its modern architecture built on Rust, offering superior speed and memory efficiency. Polars' lazy evaluation and method-chaining API enable expressive, automatically-optimized data pipelines. This choice demonstrates awareness of emerging tools in data science while maintaining practical efficiency for exploratory analysis.

### Modeling: **Scikit-learn 1.5.x**
Scikit-learn was chosen for its robust Pipeline implementation that automatically prevents data leakage, consistent API across regression types, and comprehensive metrics ecosystem. The mature, well-documented framework ensures reproducibility and integrates seamlessly with our modern data processing stack.

### Environment: **DevContainer + UV**
Reproducible development environment using Docker containers and UV package manager, ensuring consistent builds across different machines and eliminating "works on my machine" issues.

---

## Repository Structure

```
.
├── .devcontainer/
│   ├── devcontainer.json
│   └── Dockerfile
├── data/
│   └── winequality-red.csv (downloaded separately)
├── notebooks/
│   └── main.ipynb          # Main analysis notebook
├── outputs/                # Generated plots and results
├── pyproject.toml          # UV project configuration
├── uv.lock                 # Locked dependencies
├── README.md               # This file
└── .gitignore
```

---

## Setup Instructions

### Prerequisites
- **Docker Desktop** installed and running
- **Visual Studio Code** with Dev Containers extension
- **Git** configured

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/[USERNAME]/ml-project-wine-quality.git
   cd ml-project-wine-quality
   ```

2. **Open in DevContainer**
   - Open the folder in VSCode
   - When prompted, click **"Reopen in Container"**
   - Wait for container build (~3-5 minutes first time)
   - Container is ready when you see Python 3.11 in the status bar

3. **Verify installation**
   ```bash
   python --version          # Should show: Python 3.11.x
   python -c "import polars; print(polars.__version__)"     # Should show: 1.8.x
   python -c "import sklearn; print(sklearn.__version__)"   # Should show: 1.5.x
   ```

4. **Run the notebook**
   - Open `notebooks/main.ipynb`
   - Select kernel: **Python 3.11 (.venv)**
   - Run All Cells

---

## Results Summary

> **Note**: Results will be populated after model training in Phase 4-5

### Linear Regression
| Metric | Value |
|--------|-------|
| R² (Test) | TBD |
| MAE | TBD |
| RMSE | TBD |

### Logistic Regression
| Metric | Value |
|--------|-------|
| Accuracy | TBD |
| Precision | TBD |
| Recall | TBD |
| F1-Score | TBD |
| ROC-AUC | TBD |

---

## AI Usage Disclosure

**Tool Used**: Claude 3.7 Sonnet (Anthropic) + Antigravity Agent (Google IDX)

**Tasks Assisted**:
- DevContainer configuration and Dockerfile setup
- Dependency management with UV and pyproject.toml structure
- Code templates for preprocessing pipeline and model implementation
- Visualization boilerplate for EDA section
- Metrics calculation scaffolding
- Documentation structure and README formatting

**Human Contribution**:
All generated code was thoroughly reviewed, tested, and understood by both team members. We can explain every line of code in the notebook, made deliberate modifications to fit our specific analysis needs, and verified all outputs for correctness. The AI served as a productivity tool, not a replacement for understanding.

---

## Team Contributions

**Andrés Quisilema**:
- Repository setup and DevContainer configuration
- Data acquisition and initial exploration
- Linear regression implementation and analysis
- Code quality review and testing

**José Quishpe**:
- Preprocessing pipeline development
- Exploratory Data Analysis (EDA) visualizations
- Logistic regression implementation and metrics
- Documentation and README finalization

Both members contributed equally to all aspects of the project and can explain any section in detail.

---

## Project Status

- [x] Phase 1: Repository setup and DevContainer
- [ ] Phase 2: Data acquisition and loading
- [ ] Phase 3: Exploratory Data Analysis
- [ ] Phase 4: Linear Regression modeling
- [ ] Phase 5: Logistic Regression modeling
- [ ] Phase 6: Final documentation and validation

---

## License
This project is submitted as coursework for Machine Learning (6 SIN-A) at Escuela Politécnica Nacional. All code is available for educational purposes.

---

**Last Updated**: 2026-05-11
