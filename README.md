# R Code Samples - DIME RA Application
## Candidate: Kadidja Sidibé

---

I’ve put together this repository to serve as a map for my code samples using R programming software. I selected these specific scripts from a project I’m working on regarding education in West Africa because they best show how I handle the full data cycle—from raw, messy surveys to final analysis.

---

### Links to Scripts

**1. [00_master.R](https://github.com/kadidjasidibe/Education-data-analysis-in-developing-countries/blob/main/dhs/00_r_script/00_master.R)** This is the "brain" of the project. I use it to set file paths and run every script in the right order. I always include a master script to make sure the work is fully reproducible for the rest of the team.


**2. [02_a_dhs_dqa.R](https://github.com/kadidjasidibe/Education-data-analysis-in-developing-countries/blob/main/dhs/00_r_script/02_a_dhs_dqa.R)** I never start cleaning without performing a Data Quality Assessment (DQA). This script shows my process for catching outliers, duplicates and logical errors in raw DHS data before any further analysis.


**3. [03_c_spatial_merge.R](https://github.com/kadidjasidibe/Education-data-analysis-in-developing-countries/blob/main/dhs/00_r_script/03_c_spatial_merge.R)** Since the RAMP project has a big focus on geospatial data, I wanted to include this sample. It shows how I join shapefiles with household surveys and how I deal with the typical issues that come up during a spatial merge.

**4. [04_analysis_and_viz.R](https://github.com/kadidjasidibe/Education-data-analysis-in-developing-countries/blob/main/dhs/00_r_script/04_data_analysis.R)** This is where I conduct the core econometric analysis. A few things I handled here (and that are relevant to the "RAMP", "Parternship for Economic Inclusion Impact Collaborative", and "RA WBG Reproducible Research Initiative" projects) :

**Survey Weights**: Used the survey package for clusters and strata. I added a fix for "lonely PSUs" so the math doesn't break (in case we have seevral disaggregation levels).

**Fixing "Perfect Predictors"**: I found that Birth Certificates were 100% correlated with enrollment. I didn't just leave it; I checked the raw tables and adjusted the model so it could actually converge.

**Multicollinearity**: Used a correlation matrix to remove variables that were too similar (like electricity vs. poverty)

---

Environment: R (tidyverse, sf, survey)

---
Data: DHS and GIS Shapefiles
