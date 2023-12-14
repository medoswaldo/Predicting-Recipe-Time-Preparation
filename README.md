# Predicting Recipe Time Preparation
My exploratory data analysis on this dataset can be found here 	[oswalod's EDA](https://medoswaldo.github.io/recipes_and_ratings_exploratory_analysis/)

By Oswaldo Medina Jr (omedinajr@ucsd.edu)

## Framing the Problem
The chosen prediction problem involves forecasting the number of minutes required to prepare a recipe. This constitutes a regression problem, as the response variable is the continuous duration, measured in minutes, for recipe preparation, an attribute continuously associated with time. The Decision Tree Regressor will be employed to predict this duration. This regression model is selected due to the quantitative nature of all the features incorporated in the analysis. These features include the Number of Steps (`n_steps`), Number of Ingredients (`n_ingredients`), and Amount of Calories (`calories`). The decision to use the number of minutes for recipe preparation as the response variable is driven by its significance, offering users insights into and opportunities for optimizing the preparation time of recipes. This choice aims to give people a better understanding and the means to optimize the lead time for recipe preparation. Leveraging quantitative data, these features collectively contribute to predicting the time. The chosen metric for model evaluation is the Root Mean Squared Error (RMSE). RMSE is preferred due to its properties, which render it suitable for comparing different models and assessing their accuracy of fit. This choice checks its usefulness in evaluating the accuracy of predictions related to recipe preparation time.


## Baseline Model
The model I chose for my base model was a multiple-feature Decision Tree Ressessor made to precut the minutes in the original recipes dataset. The model followed the criteria of using at least two feature columns that must be transformed. I have four features: ‘n_steps’, ‘n_ingredients’, ‘more_cal_than”avg’, and ‘more_steps_than_avg’. I assumed these features were best for the base since all of their components are very straight and detailed towards knowing the process of difficulty of the recipes, and, in turn, the difficulty could be repeated with the time the recipes would take. The ‘n_ingredients’ and ‘n_steps’ are quantitative variables representing the solid amount of steps or ingredients in each recipe. In the dataset, we have added two categorical nominal variables ‘more_cal_than”avg’, and ‘more_steps_than_avg’, which caused us to OneHotEncoded these columns to ger quantitative variables that we could perform other functions on. The pipeline had a Decision Tree Regressor model that is kept in its default parameter since I didn’t believe any real action we required for the model. 


## Final Model
In enhancing the final model, I introduced the 'calories' feature under the premise that recipes with higher caloric content often demand more preparation time. This addition aims to capture nuanced correlations within the data, offering a more sophisticated understanding of the underlying data-generating process. The hypothesis is that caloric content significantly influences recipe preparation time.

To refine the model further, I applied a `QuantileTransformer()` to the 'calories' feature. This transformation mitigates skewed distributions, promoting a symmetric distribution that aids the model in grasping patterns and relationships within the data. It's especially valuable for preventing extreme values in the calorie distribution from unduly impacting the prediction task.

Additionally, I employed `StandardScaler()` on the 'n_steps' and 'n_ingredients' features to address potential scale variations. This standardization ensures equal contributions from these features during the training process, preventing any one feature from dominating the learning algorithm due to scale differences. The aim is to foster a more balanced and robust learning process.

The modeling algorithm retained the Decision Tree Regressor, which demonstrated effectiveness in the baseline model. Hyperparameter tuning involved systematically searching through a parameter grid, specifically focusing on 'max_depth,' 'min_samples_split,' and 'min_samples_leaf.' This process, facilitated by `GridSearchCV`, aimed to find the optimal balance between model complexity and performance.

The chosen hyperparameters yielded a final RMSE of 647.2491544, showcasing an improvement over the baseline model and affirming the effectiveness of the introduced features and model refinements.


## Fairness Analysis


