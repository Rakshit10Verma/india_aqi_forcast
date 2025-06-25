# Predictive Modeling of Air Quality in India

## Overview

This project presents an end-to-end data science pipeline for forecasting the daily Air Quality Index (AQI) in Delhi, India. Air pollution is a critical public health issue in the region, and this project aims to provide a reliable tool for short-term prediction (24 hours in advance) to aid public policy and health advisories.

The project leverages a five-year historical dataset of air quality metrics and employs machine learning to build and evaluate predictive models. The final model, an optimized XGBoost Regressor, demonstrates high accuracy in forecasting future AQI values.

This repository contains all the necessary data, code, notebooks, and the final report for complete reproducibility.

## Features

- **Data Cleaning & Preprocessing:** A documented pipeline for cleaning raw time-series data from the CPCB.
- **Exploratory Data Analysis (EDA):** In-depth analysis of seasonal trends, pollutant correlations, and AQI distribution.
- **Feature Engineering:** Creation of time-lag and rolling-window features to capture temporal dependencies.
- **Model Benchmarking:** A comparative analysis of four regression models:
  - Linear Regression (Baseline)
  - Lasso Regression
  - LightGBM
  - XGBoost (Best performing model)
- **Evaluation:** Robust evaluation using a chronological train-test split and standard regression metrics (RMSE and R²).
- **Final Report:** A detailed academic report (~2500 words) summarizing the project's methodology, findings, and implications.

## Installation

To set up the project locally, please follow these steps. This project was built using Python 3.9.

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/Rakshit10Verma/aqi-india-forecast.git
    cd aqi-india-forecast
    ```

2.  **Create and Activate a Virtual Environment**
    It is highly recommended to use a virtual environment to manage dependencies and avoid conflicts.

    *   On macOS/Linux:
        ```bash
        python3 -m venv venv
        source venv/bin/activate
        ```
    *   On Windows:
        ```bash
        python -m venv venv
        .\venv\Scripts\activate
        ```

3.  **Install Required Packages**
    All project dependencies are listed in the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```

4.  **Download the Dataset**
    The raw data is sourced from Kaggle. You will need to have the Kaggle API set up.
    *   Follow the instructions [here](https://www.kaggle.com/docs/api) to set up your `kaggle.json` API token.
    *   Then, run the following command from the project root to download and unzip the data into the `data/raw/` directory:
        ```bash
        kaggle datasets download -d rohanrao/air-quality-data-in-india -p data/raw/ --unzip
        ```

## Usage

The project is structured into Jupyter Notebooks that should be run in order.

1.  **Data Cleaning (`01-Data_Acquisition_and_Cleaning.ipynb`)**
    *   This notebook loads the raw data, handles missing values, and saves the cleaned dataset for Delhi.
    *   Run all cells in this notebook to generate `data/processed/delhi_aqi_cleaned.csv`.

2.  **Exploratory Data Analysis (`02-Exploratory_Data_Analysis.ipynb`)**
    *   This notebook performs a deep dive into the cleaned data, generating all the plots and insights used in the final report.
    *   It creates an enhanced dataset with time-based features at `data/processed/delhi_aqi_enhanced.csv`.

3.  **Modeling and Evaluation (`03-Modeling_and_Evaluation.ipynb`)**
    *   This notebook implements the full modeling pipeline: feature engineering, training the four models, and evaluating their performance.
    *   Running this notebook will produce the final performance metrics and save key visuals (like prediction plots and feature importance) to the `reports/figures/` directory.

## Project Structure
