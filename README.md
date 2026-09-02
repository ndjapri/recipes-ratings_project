# recipes-ratings_project
A project containing a dataset of recipes and interactions/ratings of the given recipes for the DSC 80 course at UCSD.

# What Makes a Recipe Highly Rated?

Nathaniel Djapri

## Introduction

The dataset contains recipes and user ratings from Food.com. Each row represents a recipe, along with information about its ingredients, preparation, description, tags, and user ratings.

The main question my project is centered around is: **Do recipes with specific tags tend to get better ratings?** Understanding this relationship can help me identify whether certain characteristics or categories associated with recipes are related to how highly users rate them.

The dataset contains **83,782 recipes**. The columns most relevant to our analysis are:

- **`tags`** — tags describing characteristics or categories associated with a recipe.
- **`avg_rating`** — the average user rating for each recipe.
- **`minutes`** — the amount of time required to prepare the recipe.
- **`ingredients`** — the ingredients used in the recipe.
- **`description`** — the written description of the recipe.

These variables are used to explore the patterns in recipe ratings and investigate whether recipes associated with particular tags tend to receive higher ratings.

## Data Cleaning and Exploratory Data Analysis

### Data Cleaning

The recipe data was first combined with the user interaction data so that each recipe could be analyzed together with its ratings. The interaction data contains user ratings, while the recipe data contains information such as ingredients, preparation time, tags, and descriptions.

Any rating of `0` is replaced with `NaN` so that it would not incorrectly lower the average rating of a recipe. This is done because a rating of `0` does not represent a genuine zero-star rating in this dataset. Instead, it indicates that a rating was not provided.

The average rating was then calculated for each recipe using its available user ratings, and this value was added to the recipe dataset as `avg_rating`. The `tags` column was also converted into lists so that individual tags could be analyzed across recipes.

After cleaning and calculating average ratings, **81,173 recipes had an available average rating**.

The following cleaned variables were used throughout the analysis:

- `avg_rating` — the average rating received by a recipe.
- `n_ingredients` — the number of ingredients used in a recipe.
- `minutes` — the preparation time in minutes.
- `tags` — descriptive tags associated with each recipe.
- `description` — the written description of each recipe.

### Univariate Analysis

The distributions of average recipe ratings and number of ingredients were examined separately.

#### Average Rating

<iframe
src="assets/avg_rating_histogram.html"
width="800"
height="600"
frameborder="0"
></iframe>

The distribution of average ratings is heavily concentrated at the upper end of the rating scale. The mean rating is **4.63**, while the median is **5.0**, and 75% of recipes have a rating of 5.0. This indicates that recipes in the dataset generally receive very high ratings, with relatively few recipes receiving ratings below 4.

#### Number of Ingredients

<iframe
src="assets/n_ingredients_histogram.html"
width="800"
height="600"
frameborder="0"
></iframe>

The number of ingredients is concentrated around relatively small values. A recipe uses an average of **9.21 ingredients**, with a median of **9 ingredients**, while the middle 50% of recipes use between **6 and 11 ingredients**. The distribution is right-skewed, with a smaller number of recipes using substantially more ingredients, reaching as high as 37.

### Bivariate Analysis

Relationships between pairs of variables were examined to identify possible associations with recipe ratings.

#### Number of Ingredients vs. Average Rating

<iframe
src="assets/ingredients_vs_rating.html"
width="800"
height="600"
frameborder="0"
></iframe>

There does not appear to be a strong relationship between the number of ingredients and average rating. Recipes with both few and many ingredients can receive high or low ratings, suggesting that the number of ingredients alone may not be a strong predictor of recipe ratings.

#### Recipe Tags vs. Average Rating

<iframe
src="assets/top_tags_boxplot.html"
width="800"
height="600"
frameborder="0"
></iframe>

The distributions of average ratings are similar across the most common recipe tags, with most recipes receiving ratings near 4.5–5.0. Although some tags have slightly different distributions, there is no large difference in ratings across these common categories.

### Interesting Aggregates

Recipes were grouped by their tags, and both the number of recipes and average rating were calculated.

#### Top 10 Highest-Rated Tags
![Grouped Table](assets/grouped_table_1.png)

#### Top 10 Lowest-Rated Tags
![Grouped Table](assets/grouped_table_2.png)

The grouped tables show that average ratings differ somewhat across recipe tags. The highest-rated tags have average ratings between about 4.77 and 4.97, with `hidden-valley-ranch` having the highest average rating at 4.97. The lowest-rated tags shown have average ratings between about 4.53 and 4.58, with `crock-pot-slow-cooker` having the lowest average rating at 4.53. Overall, the differences are relatively small, suggesting that recipe tags may be associated with ratings, but the tag alone does not determine whether a recipe receives a high rating.

## Assessment of Missingness

## Hypothesis Testing

## Framing a Prediction Problem

## Baseline Model

## Final Model

## Fairness Analysis