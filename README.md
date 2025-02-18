# MHAS Migration and Cognition Analysis

This repository contains code for analyzing cognitive trajectories of older Mexican adults based on migration status, using the Mexican Health and Aging Study (MHAS) dataset.

## Project Overview

The analysis explores how return migration affects cognitive pathways of older Mexican adults, with a specific focus on the Salmon Bias hypothesis. We examine whether there are differences in cognitive trajectories between Mexican-born individuals who migrated to the US (return migrants) and non-migrants, and whether reasons for migration impact cognitive trajectories.

## Data Source

The Mexican Health and Aging Study (MHAS) is a longitudinal national study of adults aged 50 and older living in Mexico. Data collection spans six waves:
- Wave 1: 2001
- Wave 2: 2003
- Wave 3: 2012
- Wave 4: 2015
- Wave 5: 2018
- Wave 6: 2021

## Cognitive Measures

The analysis examines several cognitive domains:
- Psychomotor speed (Visual Scan task)
- Visuospatial ability (Drawing task)
- Working memory (Immediate Recall)
- Long-term memory (Delayed Recall)
- Visual memory (Visual Recall)

## Code Structure

The R script processes MHAS data through the following steps:

1. **Data Import and Preparation**: Loads SAS datasets for each wave
2. **Variable Standardization**: Renames variables for consistency across waves
3. **Migration Variables**: Processes variables related to:
   - Years lived in the US
   - Reasons for return migration
   - Migration status
4. **Cognitive Assessment**: Processes cognitive test variables
5. **Data Merging**: Combines all waves into a longitudinal dataset

## Dependencies

The code requires the following R packages:
- haven (for reading SAS datasets)
- tidyverse (for data manipulation)
- *tidylog (for logging data transformations)
- magrittr (for pipe operations)
- dplyr (for data manipulation)
- data.table (for efficient data handling)
- psych (for statistical functions)
- sjmisc (for merging datasets)
  * = Not necessary but will help with tracking changes. 
## Key Variables

### Migration Variables
- `lived_us`: Whether participant lived in the US
- `yrslived_us`: Number of years lived in the US
- `return_us_first`: Age of first return to Mexico
- Reason for return variables (e.g., `reasonR_ill`, `reasonR_missF`, `reasonR_diff`)

### Cognitive Variables
- Immediate recall tests (`Ima_1`, `Ima_2`, `Ima_3`, etc.)
- Delayed recall tests (`delay_a`, `delay_b`)
- Visual scan test (`v_scan`)
- Drawing test (`draw`)
- Visual recall test (`v_recall`)

## Analysis Approach

Our analytical approach uses multi-level modeling to examine:
1. Differences in cognitive trajectories between return migrants and non-migrants
2. Whether different reasons for migration affect cognitive trajectories among return migrants

## Research Questions

1. Are there differences in cognitive trajectories between Mexican-born individuals who migrated to the US (return migrants) and non-migrants?
2. Among return migrants, are there differences in cognitive level and change based on reason for migration?

## Usage

The data processing script creates a longitudinal dataset (`mhas_cd`) that can be used for statistical analysis in R or exported to other statistical software like SAS for multilevel modeling.

## ABOUT MHAS

For more information related to the Mexican Health and Aging Study, please visit https://www.mhasweb.org/Home/index.aspx 
Wong, R., Michaels-Obregon, A., & Palloni, A. (2017). Cohort profile: the Mexican health and aging study (MHAS). International journal of epidemiology, 46(2), e2-e2. 
