# NIA T32 Landscape Analysis

[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg)](https://www.python.org/)
[![Jupyter Notebook](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

A reproducible workflow for analyzing the research landscape of NIH NIA T32 institutional training grants using NIH RePORTER, PubMed, and VOSviewer.

---

## Overview

This repository contains a Jupyter Notebook that automates much of the workflow required to characterize a portfolio of NIH T32 training grants.

The workflow:

- retrieves grant information from NIH RePORTER
- retrieves associated publications from PubMed
- prepares text files for bibliometric mapping in VOSviewer
- summarizes research themes and collaboration clusters
- identifies measurement and psychometric terminology across publication clusters

The notebook was designed to support landscape analyses for strategic planning, program evaluation, and grant development.

---

## Workflow

```text
grants.csv
      │
      ▼
NIH RePORTER API
      │
      ▼
Grant metadata
      │
      ├──────────────► Excel summary
      │
      ▼
Publication PMIDs
      │
      ▼
PubMed API
      │
      ▼
MEDLINE records
      │
      ▼
VOSviewer
      │
      ▼
Network Map
      │
      ▼
Cluster & Measurement Analysis
      │
      ▼
Charts + Summary Tables
```

---

## Repository Structure

```
FSM_NIA-T32-Landscape-Analysis/

│
├── NIA_T32_Landscape_Analysis.ipynb
├── README.md
├── LICENSE
├── CITATION.cff
├── requirements.txt
│
├── data/
│     └── grants.csv
│
├── output/
│     ├── nih_reporter/
│     ├── vosviewer_input/
│     ├── vosviewer_output/
│     ├── charts/
│     └── measurement_analysis/
```

---

## Requirements

Python 3.11+

Required packages:

- pandas
- requests
- matplotlib
- tqdm
- openpyxl

Install with

```bash
pip install -r requirements.txt
```

---

## Input Data

Provide a CSV file named

```
data/grants.csv
```

containing a column named

```
Project Number
```

Example

| Project Number |
|----------------|
| T32AG000181 |
| T32AG000213 |
| T32AG000555 |

---

## Running the Notebook

1. Clone the repository

```bash
git clone https://github.com/kglibrarian/FSM_NIA-T32-Landscape-Analysis.git
```

2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Add

```
data/grants.csv
```

4. Open

```
NIA_T32_Landscape_Analysis.ipynb
```

5. Run all cells.

---

## VOSviewer

After the notebook creates the MEDLINE file

```
output/vosviewer_input/grant_publications_medline.txt
```

Open this file in VOSviewer.

Export the network map to

```
output/vosviewer_output/
```

The notebook expects

```
vosviewer_map_file_pubs.txt
```

---

## Outputs

The notebook produces

- NIH RePORTER summaries
- publication lists
- MEDLINE files
- VOSviewer input files
- bibliometric maps
- publication cluster summaries
- measurement term analyses
- publication-quality figures

---

## Reproducibility

The repository intentionally excludes

```
data/
output/
```

from version control.

Users should supply their own grant list and regenerate all analyses locally.

---

## Citation

If you use this workflow, please cite this repository.

A DOI will be added after Zenodo archiving.

---

## Author

Karen E. Gutzman

Metrics & Impact Core

Galter Health Sciences Library & Learning Center

Northwestern University Feinberg School of Medicine

---

## License

This project is licensed under the MIT License.
