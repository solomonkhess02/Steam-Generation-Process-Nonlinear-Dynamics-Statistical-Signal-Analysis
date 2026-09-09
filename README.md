# Steam Generation Process: Nonlinear Dynamics & Statistical Signal Analysis

Research project on the analysis and prediction of steam temperature in a thermal power plant using nonlinear dynamics, statistical analysis, and machine learning.

## Overview

A thermal power plant is a complex dynamical system in which multiple process parameters continuously interact and change with operating conditions.

This project analyzes high-frequency process data from a thermal power plant to understand the dynamic behavior of the steam-generation process and identify process variables that are relevant to superheater steam-temperature prediction.

The work combines:

- Nonlinear dynamical-system analysis
- Statistical signal analysis
- Feature selection
- Time-series analysis
- Regression and neural-network modeling
- Sliding-window prediction

The longer-term objective of this line of work is to support process understanding and future control-strategy development for flexible power generation.

## Dataset

The analysis uses one month of thermal power plant process data.

- **Duration:** 31 days
- **Process parameters:** 96
- **Sampling interval:** 30 seconds
- **Observations per parameter:** 89,291
- **Target variable:** Superheater Steam Temperature (Line-A)

The process operates under normal-load and low-load conditions, allowing the analysis to examine how system dynamics change with operating state.

> **Data Availability:** The underlying industrial plant data is not included in this repository.

## Research Questions

The project investigates several questions:

1. Are the process signals stationary or dynamically changing?
2. Do the signals exhibit persistence or nonlinear behavior?
3. How do process dynamics change between normal-load and low-load operation?
4. Which process variables are most relevant to superheater steam temperature?
5. Can statistical and machine-learning models predict steam temperature under changing operating conditions?
6. Can dynamic feature selection improve prediction for a non-stationary process?

## Methodology

### 1. Process and Signal Analysis

The process signals are first analyzed to characterize their dynamic behavior.

Methods include:

- Stationarity analysis
- Time-lag analysis
- Hurst exponent
- State-space analysis
- Sliding-window analysis
- Root Mean Square (RMS) analysis
- Dynamics Similarity Index (DSI)
- Chaotic Dynamics Marker (CDM)

These analyses are used to understand how the process state changes with time and operating load.

### 2. Statistical Analysis and Feature Selection

Several statistical methods are used to identify influential process variables:

- Ordinary Least Squares (OLS) regression
- t-value based analysis
- Minimum Redundancy Maximum Relevance (mRMR)
- Covariance analysis
- Akaike Information Criterion (AIC)

The objective is to identify process variables that provide useful information for superheater steam-temperature prediction while reducing redundant features.

### 3. Steam Temperature Prediction

Prediction models explored in the study include:

- Multiple Linear Regression (MLR)
- Artificial Neural Network (ANN)

Both fixed-feature and dynamically selected-feature configurations are investigated.

### 4. Sliding-Window Modeling

Because the process is non-stationary, a fixed set of variables may not remain equally informative throughout the operating period.

A sliding-window approach is therefore used to dynamically select process variables based on statistical significance and predict future steam-temperature values.

The analysis investigates different training-window, step-size, and prediction-window configurations under normal and low-load conditions.

## Key Findings

The analysis indicates that:

- The process signals are generally **non-stationary**.
- Steam-temperature dynamics vary with operating load.
- Steam temperature shows **persistent behavior**, with stronger persistence observed during low-load operation.
- The time lag of the steam-temperature signal changes across successive windows.
- **Burner Tilt, Spray Flow, and Secondary Air Temperature** emerge as important variables for steam-temperature prediction.
- Other potentially useful variables include Total Air Flow and Total Mainstream Steam Flow depending on operating condition.
- Dynamic feature selection can improve prediction compared with using a fixed set of variables over longer prediction intervals.
- Shorter prediction windows can be more suitable when process dynamics change rapidly.

## Results

Prediction performance is evaluated using:

- **R²**
- **Mean Absolute Error (MAE)**

The analysis shows substantial variation in prediction performance across operating windows, highlighting the effect of changing process dynamics.

For normal-load conditions, a large majority of prediction windows show meaningful correlation between predicted and actual steam temperature, while low-load conditions exhibit greater variability.

## Repository Structure

```text
Steam-Generation-Process-Nonlinear-Dynamics-Statistical-Signal-Analysis/
│
├── README.md
├── notebooks/
│   ├── signal_analysis/
│   ├── statistical_analysis/
│   └── prediction/
│
├── src/
│   ├── signal_analysis/
│   ├── feature_selection/
│   └── prediction/
│
├── figures/
│
└── docs/
