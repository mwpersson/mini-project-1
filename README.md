# Bike Sharing Demand Prediction

## Project Overview
This project analyzes and predicts bike rental demand using the UCI Bike Sharing Dataset. The goal is to build regression models that accurately forecast hourly bike rentals based on temporal and weather features.

## Dataset
- **Source**: [UCI Bike Sharing Dataset](https://archive.ics.uci.edu/dataset/275/bike+sharing+dataset)
- **Type**: Hourly bike rental data
- **Years**: 2011-2012
- **Target Variable**: `cnt` (total bike rentals)

## Project Structure
```
mini-project-1/
├── data/
│   ├── day.csv
│   └── hour.csv
├── notebooks/
│   ├── 01_exploration.ipynb
│   └── 02_modeling.ipynb
└── README.md
```

## Notebooks

### 01_exploration.ipynb
Data exploration and visualization:
- Correlation analysis
- Temporal patterns (hourly, seasonal)
- Weather impact analysis
- Distribution analysis by temperature and humidity

### 02_modeling.ipynb
Model development and evaluation:
- Baseline Linear Regression
- Feature Engineering (sinusoidal temporal features)
- Polynomial Features (degree 3)
- Regularization (Ridge & Lasso)

## Key Features
- **Temporal**: Hour, month (with sinusoidal encoding)
- **Weather**: Temperature, humidity, wind speed, weather situation
- **Calendar**: Holiday, working day, weekday

## Models Evaluated
1. **Baseline Linear Regression**
2. **Linear Regression + Sinusoidal + Polynomial Features**
3. **Ridge Regression** (α = 0.1, 1.0, 10.0)
4. **Lasso Regression** (α = 0.1, 1.0, 10.0)

## Setup Instructions
1. Clone or download this repository
2. Install required dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn scikit-learn
    ```
3. Open and run notebooks in order:
    - `01_exploration.ipynb` for exploratory data analysis
    - `02_modeling.ipynb` for model training and evaluation

## Evaluation Metrics

- **RMSE** (Root Mean Squared Error)
- **MAE** (Mean Absolute Error)
- **R²** (Coefficient of Determination)

## Results Summary

The sinusoidal and polynomial feature model showed significant improvement over the baseline.

### Model Comparison

| Model | RMSE | MAE | R² |
|-------|------|-----|-----|
| Lasso (α=0.1) | 90.385409 | 63.814183 | 0.742005 |
| Ridge (α=10.0) | 90.525734 | 63.909343 | 0.741203 |
| Ridge (α=1.0) | 90.596337 | 63.962193 | 0.740799 |
| Ridge (α=0.1) | 90.606310 | 63.969145 | 0.740742 |
| Linear Regression (sin+poly) | 90.607468 | 63.969939 | 0.740736 |
| Lasso (α=1.0) | 91.679555 | 64.223806 | 0.734564 |
| Lasso (α=10.0) | 104.404205 | 73.952131 | 0.655768 |
| Linear Regression (baseline) | 153.379853 | 115.057467 | 0.257064 |

## Requirements
```
pandas
numpy
matplotlib
seaborn
scikit-learn
```

## Team Contribution

- Timothy Tan - Data Exploration
- Michael Persson - Feature Engineering, Model Training, Model Evaluation