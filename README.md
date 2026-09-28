# Data and Code Repository

## Overview

This repository contains the data and code used to reproduce the main and supplementary results reported in the associated manuscript.

The repository reproduces:

- Table 1
- Supplementary Tables 2-9
- Figures 1-3
- Supplementary Figures 1-2

## Repository structure

```text
.
|-- README.md
|-- Data/
|   |-- choice-set1.dta
|   |-- choice-set2.dta
|   |-- choice-set3.dta
|   |-- count_regression_sample.dta
|   |-- Figure.xlsx
|   |-- only_urban_sample.dta
|   `-- selective_attrition_sample.dta
`-- Code/
    |-- Tables.do
    |-- Fig1.py
    |-- Fig2.py
    |-- Fig3.py
    |-- Supplementary_Fig1.py
    `-- Supplementary_Fig2.py
```

## Data files

| File | Description |
| --- | --- |
| `choice-set1.dta` | Primary choice-set data used for Table 1 and Supplementary Tables 2-4 and 7-9. |
| `choice-set2.dta` | Alternative choice-set data used for Table 1 and Supplementary Table 4. |
| `choice-set3.dta` | Alternative choice-set data used for Table 1 and Supplementary Table 4. |
| `only_urban_sample.dta` | Urban-township subsample used for Supplementary Table 3. |
| `count_regression_sample.dta` | Count-regression sample used for Supplementary Table 5. |
| `selective_attrition_sample.dta` | Sample used for the selective-attrition analysis in Supplementary Table 6. |
| `Figure.xlsx` | Source data used by the Python scripts to generate Figures 1-3 and Supplementary Figures 1-2. |

## Code files

| File | Description |
| --- | --- |
| `Tables.do` | Stata code for Table 1 and Supplementary Tables 2-9. |
| `Fig1.py` | Generates `Fig1.png` from sheets `Fig1_a` and `Fig1_b`. |
| `Fig2.py` | Generates `Fig2.png` from sheets `Fig2_a` and `Fig2_b`. |
| `Fig3.py` | Generates `Fig3.png` from sheet `Fig3`. |
| `Supplementary_Fig1.py` | Generates `Fig_S1.png` from sheet `Fig_S1`. |
| `Supplementary_Fig2.py` | Generates `Fig_S2.png` from sheet `Fig_S2`. |

## Software requirements

### Tables

- Stata
- User-written Stata commands used by `Tables.do`: `vce2way`, `mixlogit`, `vcemway`, `ppmlhdfe`, and `reghdfe`

### Figures

- Python 3
- `matplotlib`
- `numpy`
- `pandas`
- `openpyxl`

## Reproducing the tables

Start Stata, set the working directory to the repository's `Data/` directory, and run the do-file from there:

```stata
cd "/path/to/repository/Data"
do "../Code/Tables.do"
```

The regression estimates are displayed in the Stata Results window. `Tables.do` sets the random-number seed used for the mixed-logit analysis.

## Reproducing the figures

From the repository root, run:

```bash
python Code/Fig1.py
python Code/Fig2.py
python Code/Fig3.py
python Code/Supplementary_Fig1.py
python Code/Supplementary_Fig2.py
```

Each script reads the plotting data from `Data/Figure.xlsx` and writes the corresponding PNG file to the `Code/` directory.
