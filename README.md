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

#### Recipe Ratings by Cooking Time

| Cooking Time Category | Average Rating | Recipe Count | Average Minutes |
|----------------------|----------------|--------------|-----------------|
| Very Quick (<15m)    | 4.67           | 16,303      | 9.33           |
| Quick (15-30m)       | 4.62           | 20,115      | 24.87          |
| Medium (30-60m)      | 4.61           | 24,570      | 45.68          |
| Long (60-120m)       | 4.63           | 11,840      | 81.71          |
| Very Long (>120m)    | 4.59           | 8,344       | 779.34         |

#### Recipe Complexity Analysis

| Cooking Time Category | Avg Ingredients | Avg Steps | Avg Calories |
|----------------------|-----------------|-----------|--------------|
| Very Quick (<15m)    | 6.48           | 5.55      | 313.49       |
| Quick (15-30m)       | 8.88           | 9.34      | 375.64       |
| Medium (30-60m)      | 10.09          | 11.49     | 445.81       |
| Long (60-120m)       | 10.97          | 13.14     | 558.00       |
| Very Long (>120m)    | 10.19          | 12.31     | 553.61       |

#### Missing Value Analysis

| Column               | Missing Count | Missing Percentage |
|---------------------|---------------|-------------------|
| name                | 1             | 0.00%             |
| description         | 70            | 0.08%             |
| avg_rating          | 2,609         | 3.11%             |
| cooking_time_category| 1             | 0.00%             |
| time_category       | 1             | 0.00%             |

- *Note: Only columns with missing values are shown. All other columns have complete data.*

Key insights from this data:
- Very quick recipes (<15 minutes) have the highest average rating (4.67)
- Longer cooking times correlate with more complex recipes (more ingredients and steps)
- Missing data is minimal, with only 3.11% missing ratings being the highest percentage
- Recipe complexity generally increases with cooking time, but plateaus for very long recipes

  
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


