# A County-Level Suitability Analysis for New Data Center Sites in the United States

Authors: Jacob Mckenna, Jyothir Krishnan, Joel Harder

This repository contains the code and methodology for a GIS-based suitability model designed to systematically evaluate and identify optimal locations for new data center sites across the contiguous United States. This project was prepared for GEOG*4480 - Applied Geomatics.

## Git & Jupyter Collaboration Workflow
Because we are collaborating on `.ipynb` files, we use **nbdime** to handle version control and prevent base64 output noise or merge conflicts from corrupting our notebooks.

### Setup (Run Once Locally)
1. Install the package: `pip install nbdime`
2. Configure Git for this specific repository: `nbdime config-git --enable`

## Methodology
The analysis shifts the focus from purely economic optimization toward geographic suitability. We utilize a Weighted Linear Combination (WLC) Multi-Criteria Evaluation model implemented at the county level. 

Key physical and infrastructure variables are standardized to a 0.0 to 1.0 suitability scale. These variables include:
* Slope
* Access to electricity and cost of electricity
* Proximity to water
* Broadband availability
* Climate (warm-season average temperature)
* Likelihood of natural disasters
* Transportation infrastructure

All spatial datasets are projected into EPSG:5070 (NAD83 / Conus Albers). They are then standardized and summarized to a single county boundary layer to ensure fair and consistent ranking across the contiguous United States.

![Methods Flowchart](./methods_flowchart.drawio.svg)

## Tech Stack
* **Language:** Python
* **Environment:** Jupyter Notebooks
* **GIS Library:** `arcpy`
