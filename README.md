# 🥠 COVID-19 Global Data Analysis and Time Series Forecasting

## Project Overview

This repository hosts a data science project dedicated to the analysis and short-term forecasting of the global COVID-19 pandemic. Using publicly available time-series data from **Johns Hopkins University (JHU) CSSE)**, the project performs in-depth Exploratory Data Analysis (EDA) to visualize trends, track key metrics, and ultimately implements a machine learning model for case prediction.

The primary objective is to transform raw, cumulative data into actionable insights, focusing on the rate of spread and predicting future confirmed cases using advanced regression techniques.

---

## 📁 Repository Contents

| File Name                      | Description                                                                                                                                                    |
| :----------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `Code-Covid-19 Analysis.ipynb` | The main Jupyter Notebook containing all data loading, cleaning, EDA, visualization code, and the implementation of the Support Vector Regression (SVR) model. |
| `README.md`                    | This document, providing an overview of the project, methodology, and dependencies.                                                                            |

---

## 💻 Methodology & Key Analysis Steps

The **`Code-Covid-19 Analysis.ipynb`** notebook systematically processes the data through the following phases:

### 1. Data Acquisition and Preprocessing

* **Data Sources**: Data is loaded directly from the JHU CSSE GitHub repository using pandas `read_csv` for global time-series data on **Confirmed Cases** and **Deaths**.
* **Feature Engineering**: The notebook transforms the cumulative daily case counts into **Daily New Cases** and **Daily New Deaths**, which are essential for true trend analysis.
* **Data Aggregation**: All time-series data is aggregated to a global level (summed across all countries) to create a single time-series for forecasting.

### 2. Exploratory Data Analysis (EDA)

* **Time Series Analysis**: Visualization of the raw and smoothed time series for confirmed cases and deaths.
* **Trend Smoothing**: A **7-day rolling/moving average** is calculated and applied to the daily new cases and deaths to smooth out weekend reporting variations and clearly identify underlying trends.
* **Geographic Analysis**: Visualization of case distributions, including plots for the **Top 10 Most Affected Countries** and analysis of confirmed cases across different US states/provinces (which involves a logarithmic transformation for better visualization of skewed data).

### 3. Time Series Forecasting (SVR Model)

* **Model Selection**: A **Support Vector Regression (SVR)** model is chosen for short-term prediction.
* **Kernel**: A **polynomial kernel** is utilized for the SVR model, indicating that the relationship between time and cases is non-linear.
* **Training**: The model is trained on the historical daily confirmed case data.
* **Prediction**: The trained model is used to forecast the number of confirmed cases for a set number of future days.
* **Evaluation**: The model's performance is evaluated using standard regression metrics such as **Mean Absolute Error (MAE)** and **Mean Squared Error (MSE)**.

---

## 🫠 Required Dependencies

To run the `Code-Covid-19 Analysis.ipynb` notebook locally, you need a Python environment with the following libraries.

You can install them via `pip`:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

| Library                  | Purpose                                                                                     |
| :----------------------- | :------------------------------------------------------------------------------------------ |
| `pandas`                 | Data manipulation and cleaning, especially handling time-series data.                       |
| `numpy`                  | Numerical operations, array handling.                                                       |
| `matplotlib` & `seaborn` | Data visualization for generating time-series plots and bar graphs.                         |
| `scikit-learn`           | Machine learning implementation, specifically the SVR model and related metrics.            |
| `datetime`               | Handling and formatting date objects for plotting.                                          |
| `math`                   | Used for logarithmic transformations (e.g., `math.log10`) in province/state visualizations. |

---

## 🔗 Data Sources

The data used in this project is sourced from the official **Johns Hopkins University Center for Systems Science and Engineering (CSSE)** COVID-19 Data repository, reflecting the data structure present up to the last updated daily report used in the analysis (04-17-2021).

* **Global Confirmed Cases**: `time_series_covid19_confirmed_global.csv`
* **Global Deaths**: `time_series_covid19_deaths_global.csv`
* **Daily Reports**: `04-17-2021.csv` (used for latest summary statistics and detailed reports)

---

## 🚀 Get Started

### Clone the Repository

```bash
git clone [Your Repository URL]
```

### Navigate to the Directory

```bash
cd [Your Repository Name]
```

### Launch Jupyter

```bash
jupyter notebook
```

Open and run the `Code-Covid-19 Analysis.ipynb` notebook to reproduce the analysis and forecasting results.
