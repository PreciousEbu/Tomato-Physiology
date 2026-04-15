# Tomato-Physiology-Virtuaal-Population-Model
## Synthetic Tomato Population Modelling for Predicting Physiological Stress Responses Under Environmental Variability

This project develops a **synthetic tomato virtual population model** to study how environmental and management variability across locations and seasons influences key physiological traits.

The workflow demonstrates how **population simulation + machine learning modelling** can be used to analyze plant responses under data scarcity. A synthetic dataset is generated under biologically plausible assumptions, and predictive models are trained to estimate chlorophyll content, photosynthetic rate, stomatal conductance, relative water content, and fruit set performance.

---

## Motivation

Physiological responses in tomato plants vary significantly due to:

- temperature and rainfall variability
- soil moisture and soil chemistry
- seasonal differences in climate conditions
- drought stress and pathogen pressure
- irrigation and fertilizer management
- growth stage dynamics (vegetative → flowering → fruiting)

In real-world agricultural research, datasets capturing multi-location variability are often limited. This project provides a modelling pipeline that simulates realistic plant populations and enables predictive modelling under controlled assumptions.

---

## Objectives

- Simulate a synthetic tomato population dataset capturing environmental and management variability.
- Engineer drought and pathogen pressure indices.
- Predict physiological outcomes using machine learning.
- Evaluate models using MAE, RMSE, and R².
- Simulate climate stress scenarios to quantify physiological impact.

---

## Dataset Description

The dataset (`synthetic_tomato_population.csv`) contains 6,000 synthetic tomato plant samples.

### Input Features

**Categorical**
- location (Loc_1 to Loc_4)
- season (Dry/Wet)
- flowering stage (Vegetative, Flowering, Fruiting)

**Environmental Variables**
- average temperature (°C)
- rainfall (mm)
- humidity (%)
- solar radiation (MJ)
- soil moisture (%)
- soil pH
- altitude (m)

**Management Variables**
- fertilizer rate (kg/ha)
- irrigation frequency (per week)

**Plant Variables**
- plant age (weeks)
- leaf area (cm²)

**Stress Indices**
- drought stress index (0–1)
- pathogen pressure index (0–1)

---

## Targets (Physiological Outcomes)

- chlorophyll content (SPAD)
- photosynthetic rate
- stomatal conductance
- relative water content (%)
- fruit set rate (%)

---

## Methodology

### 1. Synthetic Virtual Population Generation
A synthetic dataset is generated using biologically plausible distributions.  
Location and seasonal effects are incorporated to simulate environmental variability across regions.

### 2. Stress Index Engineering
- Drought stress index is derived from rainfall and soil moisture.
- Pathogen pressure index is derived from humidity and moisture conditions.

### 3. Predictive Modelling
Multi-output regression models are trained:

- Linear Regression (baseline)
- Random Forest Regressor
- Gradient Boosting Regressor

Metrics:
- MAE
- RMSE
- R² score

### 4. Scenario Simulation (Climate Stress Experiment)
A climate stress scenario is applied:

- +2°C temperature increase
- -30% rainfall reduction
- +0.2 increase in drought stress index

Predicted physiological changes are compared to baseline conditions.

---

## Repository Structure

```bash
synthetic-tomato-physiology-model/
│
├── data/
│   └── synthetic_tomato_population.csv
│
├── notebooks/
│   └── Tomato_Physiology_Virtual_Population_Model.ipynb
│
├── src/
│   └── synthetic_population_generator.py
│
├── outputs/
│   └── figures/
│
├── README.md
└── requirements.txt
