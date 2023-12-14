# Predicting Recipe Time Preparation
My exploratory data analysis on this dataset can be found here 	[Oswalod EDA](https://medoswaldo.github.io/recipes_and_ratings_exploratory_analysis/)

By Oswaldo Medina Jr (omedinajr@ucsd.edu)

## Framing the Problem
The chosen prediction problem involves forecasting the number of minutes required to prepare a recipe. This constitutes a regression problem, as the response variable is the continuous duration, measured in minutes, for recipe preparation, an attribute continuously associated with time. The Decision Tree Regressor will be employed to predict this duration. This regression model is selected due to the quantitative nature of all the features incorporated in the analysis. These features include the Number of Steps (`n_steps`), Number of Ingredients (`n_ingredients`), and Amount of Calories (`calories`). The decision to use the number of minutes for recipe preparation as the response variable is driven by its significance, offering users insights into and opportunities for optimizing the preparation time of recipes. This choice aims to give people a better understanding and the means to optimize the lead time for recipe preparation. Leveraging quantitative data, these features collectively contribute to predicting the time. The chosen metric for model evaluation is the Root Mean Squared Error (RMSE). RMSE is preferred due to its properties, which render it suitable for comparing different models and assessing their accuracy of fit. This choice checks its usefulness in evaluating the accuracy of predictions related to recipe preparation time.


## Baseline Model


## Final Model


## Fairness Analysis


