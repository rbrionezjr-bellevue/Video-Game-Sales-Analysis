# Predicting North American Video Game Sales

## Overview

This project explores the use of predictive modeling to forecast video game sales in the North American market. The goal is to help video game developers and publishers—such as Activision, Nintendo, or Amazon Games—better understand how a new game release might perform based on historical data. These insights could be valuable for optimizing marketing strategies and guiding business decisions around product launches.

## Business Problem

**Can we predict North American video game sales using historical release data and categorical features such as platform, publisher, and genre?**

Understanding these relationships can influence:
- Marketing spend and timing
- Platform prioritization
- Post-launch performance tuning

## Data Source

- **Global Video Game Sales Dataset**  
  Sourced from Kaggle: [https://www.kaggle.com/datasets/thedevastator/global-video-game-sales](https://www.kaggle.com/datasets/thedevastator/global-video-game-sales)  
  This dataset includes global video game sales figures alongside metadata like platform, year, publisher, and genre.

## Methodology

The project followed a three-phase approach:

### 1. Exploratory Data Analysis (EDA)
- Histograms and boxplots were used to visualize platform distributions and North American sales performance.
- Initial analysis helped identify outliers and informed which features might be meaningful for modeling.

### 2. Data Preparation
- Dropped features with low predictive value (`Name`, `Rank`) and underrepresented platforms.
- Handled missing values:
  - Replaced missing years with the median year.
  - Dropped rows with missing publishers.
- Applied one-hot encoding to categorical features using `get_dummies()`.
- Removed outliers based on North American sales quartiles to improve model fit.

### 3. Model Building and Evaluation
- Employed a **multiple linear regression** model using `sklearn`.
- Target: `NA_Sales`
- Evaluated with:
  - **R-squared** (explained variance)
  - **RMSE** (prediction error)

### Results
- **Training R-squared**: 0.455
- **Test R-squared**: 0.471
- **RMSE**: ~0.084

Although RMSE was low, the R-squared value indicates that the model explains less than half the variance in North American sales. As such, the model is not suitable for deployment in its current form.

## Tools & Technologies

- Python (Jupyter Notebook)
- Pandas
- scikit-learn
- Matplotlib / Seaborn

## Limitations & Future Work

- The model lacks predictive strength (low R²). Additional or more refined features may improve results.
- Scaling of the sales data could be reconsidered.
- Future models may explore:
  - Feature engineering with time-series data
  - Alternative models (e.g., decision trees, ensemble methods)
  - Reframing the problem (e.g., classification instead of regression)

## File Descriptions

- `video_game_sales_modeling.ipynb` – Jupyter Notebook with full analysis, modeling, and visualizations
- `Final Write-Up.pdf` – Summary document including methodology, EDA, results, and reflection

---

Ruben Brionez Jr  
June 2025
