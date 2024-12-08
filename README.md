# Food Recipe Insights

Data analysis and prediction model for food recipe ratings. Final project for EECS 398 at University of Michigan.

## Project Overview

We're analyzing the Food.com recipe and rating dataset to understand what factors influence recipe ratings. The dataset contains 83,782 recipes with user ratings and detailed characteristics about each recipe.

Our analysis focuses on a key question: **What factors influence a recipe's rating on Food.com?** This question is particularly relevant in today's digital age, where home cooks increasingly rely on online recipes and reviews to guide their culinary adventures.

### Dataset Overview
* Number of recipes: 83,782
* Key features we'll examine:
   * Average rating (our target variable)
   * Cooking time
   * Number of steps and ingredients
   * Nutritional information
   * Recipe categories

### Relevant Columns
Our analysis focuses on these key features:
* `avg_rating`: The average user rating for each recipe (1-5 stars)
* `minutes`: Total cooking time required
* `n_steps`: Number of preparation steps
* `n_ingredients`: Number of ingredients used
* `calories`: Caloric content per serving
* `protein_pdv`: Protein content as percentage of daily value
* `total_fat_pdv`: Total fat content as percentage of daily value
* `carbohydrates_pdv`: Carbohydrate content as percentage of daily value
* `review_count`: Number of reviews received
* `difficulty_score`: Calculated score indicating recipe complexity

## Data Cleaning and Exploratory Data Analysis

### Dataset Overview

#### Recipe Complexity Distribution

- The distribution of recipe complexity shows that most recipes fall into the medium difficulty range (score between 0.7-1.3). There's a slight positive skew, indicating that Food.com tends to favor more approachable recipes. This aligns with the platform's focus on home cooking, where overly complex recipes might deter users.

<iframe
  src="assets/recipe_complexity.html"
  width="800"
  height="500"
  frameborder="0"
></iframe>

#### Cooking Time Impact
- Analysis of cooking time versus ratings reveals an interesting pattern: recipes with medium cooking times (30-60 minutes) tend to receive higher ratings. Very quick recipes (<15 minutes) and very long recipes (>120 minutes) show slightly lower average ratings, suggesting users prefer recipes that balance convenience with proper cooking time.

<iframe
  src="assets/rate_by_cooktime.html"
  width="800"
  height="500"
  frameborder="0"
></iframe>

### Relationship Analysis

#### Health Metrics Correlation
The relationship between nutritional values shows strong correlations between certain health metrics. Total fat and saturated fat show a strong positive correlation (0.85), while protein and carbohydrates show a weaker relationship (0.32). This suggests that recipes tend to cluster into distinct nutritional profiles.
<iframe
  src="assets/health_metrics.html"
  width="800"
  height="500"
  frameborder="0"
></iframe>

### Key Findings from EDA
- Distribution of cooking times
- Relationship between ingredients and ratings
- Nutritional content patterns
### Interesting Aggregates

Here's a summary of average ratings by cooking time category and difficulty level:

| Cooking Time | Average Rating | Number of Reviews |
|--------------|----------------|-------------------|
| Quick (<30m) | 4.61           | 2.45             |
| Medium       | 4.64           | 2.68             |
| Long (>60m)  | 4.59           | 2.71             |

This aggregation reveals that medium-length recipes not only receive higher ratings but also attract more reviews, suggesting an optimal time investment for recipe success.

### Data Imputation
We chose not to impute missing values in our analysis because:
1. The percentage of missing values was minimal (<2% across key columns)
2. Missing values appeared to be Missing Completely at Random (MCAR)
3. For our analysis questions, removing recipes with missing values wouldn't introduce significant bias
4. Maintaining data authenticity was crucial for accurate rating prediction



## Framing a Prediction Problem
We aim to predict recipe ratings based on:
- Number of ingredients
- Cooking time
- Recipe complexity
- Nutritional metrics

## Baseline Model
Our initial model uses basic recipe characteristics:
- Features: 
- Model type: Random Forest Regressor
- Performance metrics:
  - RMSE: 
  - R²: 



## Final Model
Our improved model incorporates engineered features:
- Added nutritional metrics
- Recipe complexity indicators
- Time efficiency features

Performance comparison:
- Baseline RMSE: 0.6482
- Final RMSE: 0.6360
- Improvement: 1.9%


