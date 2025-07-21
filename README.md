# data-driven-prediction-of-battery-cycle-life-before-capacity-degradation

**NOTE: For access to the modeling code, please contact Richard Braatz at braatz@mit.edu for the academic license. Only the data processing code is available without agreeing to a license.**

## Table of Contents
- [Overview](#overview)
- [Data Source](#data-source)
- [Project Structure](#project-structure)
- [Setup & Installation](#setup--installation)
- [Usage](#usage)
- [File Descriptions](#file-descriptions)
- [Contact](#contact)
- [Contributing](#contributing)

## Overview
This repository provides code to load and process data associated with the paper ['Data driven prediction of battery cycle life before capacity degradation' by K.A. Severson, P.M. Attia, et al](https://www.nature.com/articles/s41560-019-0356-8). The data is available at [https://data.matr.io/1/](https://data.matr.io/1/), where you can also find more details about the dataset.

The analysis was originally performed in MATLAB, but Python access is also provided. MATLAB files (.mat) store data in structs, while Python files (.pkl) use nested dictionaries.

## Data Source
- **Dataset:** [https://data.matr.io/1/](https://data.matr.io/1/)
- **Paper:** [Nature Energy, 2019](https://www.nature.com/articles/s41560-019-0356-8)

## Project Structure
```
Project 5/
  ├── BuildPkl_Batch1.ipynb      # Jupyter notebook for batch 1 data processing
  ├── BuildPkl_Batch2.ipynb      # Jupyter notebook for batch 2 data processing
  ├── BuildPkl_Batch3.ipynb      # Jupyter notebook for batch 3 data processing
  ├── EC_dQdV.m                  # MATLAB script for dQ/dV analysis
  ├── EC_dVdQ.m                  # MATLAB script for dV/dQ analysis
  ├── Figure4_mac.m              # MATLAB script for reproducing Figure 4
  ├── Load Data.ipynb            # Jupyter notebook for loading data
  ├── LoadData.m                 # MATLAB script for loading data
  ├── requirements.txt           # Python dependencies
  └── README.md                  # Project documentation
```

## Setup & Installation
1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd "Project 5"
   ```
2. **Set up Python environment:**
   - Using conda (recommended):
     ```bash
     conda create --name <env> --file requirements.txt
     conda activate <env>
     ```
   - Or install dependencies with pip:
     ```bash
     pip install -r requirements.txt
     ```

## Usage
- Use the `LoadData` files to load and explore the dataset.
- Jupyter notebooks (`.ipynb`) provide step-by-step data processing and analysis examples.
- MATLAB scripts (`.m`) are for advanced analysis and figure reproduction as in the original paper.

## File Descriptions
- **BuildPkl_Batch1/2/3.ipynb:** Process and convert raw data batches into Python pickle format.
- **EC_dQdV.m / EC_dVdQ.m:** MATLAB scripts for electrochemical analysis (dQ/dV and dV/dQ).
- **Figure4_mac.m:** MATLAB script to reproduce Figure 4 from the paper.
- **Load Data.ipynb / LoadData.m:** Example scripts for loading and exploring the dataset in Python and MATLAB.
- **requirements.txt:** Lists required Python packages.

## Data Structure
The data for each battery (cell) is grouped into:
- **Descriptors:** Charging policy, cycle life, barcode, channel (barcode and channel not in .pkl files).
- **Summary data:** Per-cycle info (cycle number, discharge/charge capacity, resistance, temperatures, chargetime).
- **Cycle data:** Within-cycle info (time, capacities, current, voltage, temperature, derived vectors like dQ/dV, Qdlin, Tdlin).

## Contact
For questions about the modeling code or academic license, contact:
- Richard Braatz: braatz@mit.edu

## Contributing
Contributions are welcome for data processing and analysis scripts. Please open an issue or pull request with your suggestions or improvements.
