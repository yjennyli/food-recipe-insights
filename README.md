# food-recipe-insights
Data analysis and prediction model for food recipe ratings. Final project for EECS 398 at University of Michigan

# Recipe Rating Analysis

## Introduction
This analysis investigates factors that influence recipe ratings on a popular cooking website. By analyzing recipe characteristics, nutritional content, and preparation complexity, we aim to understand what makes a recipe successful.

## Data Cleaning and Exploratory Data Analysis

### Dataset Overview
- Total recipes analyzed: [your number]
- Features examined: ingredients, cooking time, nutritional content
- Time period covered: [your range]

[Embed your first plotly visualization here using iframe]
<iframe
  src="assets/calories_by_category.html"
  width="800"
  height="500"
  frameborder="0"
></iframe>

### Key Findings from EDA
- Distribution of cooking times
- Relationship between ingredients and ratings
- Nutritional content patterns

[Embed your second plotly visualization here]

## Framing a Prediction Problem
We aim to predict recipe ratings based on:
- Number of ingredients
- Cooking time
- Recipe complexity
- Nutritional metrics

## Baseline Model
Our initial model uses basic recipe characteristics:
- Features: [list your features]
- Model type: Random Forest Regressor
- Performance metrics:
  - RMSE: [your value]
  - R²: [your value]

[Embed your feature importance plot here]

## Final Model
Our improved model incorporates engineered features:
- Added nutritional metrics
- Recipe complexity indicators
- Time efficiency features

Performance comparison:
- Baseline RMSE: 0.6482
- Final RMSE: 0.6360
- Improvement: 1.9%

[Embed your final model visualization here]
