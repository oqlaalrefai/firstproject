## Data Science Primer
This data science primer will cover exploratory analysis, data cleaning, feature engineering, algorithm selection, and model training. As you can see, those chunks make up 80% of the pie. They also set the foundation for more advanced techniques.

## Bird's Eye View

### Machine learning 
- is a comprehensive approach to solving problems..
- is a method of data analysis that automates analytical model building
- Machine learning is the practice of teaching computers how to learn patterns from data, often for making decisions or predictions.For true machine learning, the computer must be able to learn patterns that it's not explicitly programmed to identify.

*task* is a specific objective for your algorithms.
*Algorithm*  a specific ML process used to train a model.
*Model*  a set of patterns learned from data.
*Training data*  the dataset from which the algorithm learns the model.
*Test data*  a new dataset for reliably evaluating model performance.
*Features*  Variables (columns) in the dataset used to train the model.
*Target variable*  A specific variable you're trying to predict.
*Observations*  Data points (rows) in the dataset.

## Exploratory Analysis
- The two most common categories of tasks are **supervised learning** and **unsupervised learning**
- **Regression** is the task for modeling continuous target variables.
- **Classification** is the task for modeling categorical (a.k.a. "class") target variables.
- **Clustering** is the most common unsupervised learning task, and it's for finding groups within your data.
- a quick and dirty grid of **histograms** is enough to understand the distributions.
- **Categorical features** cannot be visualized through histograms. Instead, you can use **bar plots**
- **sparse classes** are classes that have a very small number of observations
- **class** is simply a unique value for a categorical feature.

- **Segmentations **
are powerful ways to observe the relationship between categorical features and numeric features.**Box plots** allow you to do so.

- **correlations **
allow you to look at the relationships between numeric features and other numeric features.
  - Positive correlation means that as one feature increases, the other increases
  - Negative correlation means that as one feature increases, the other decreases
  - Correlations near -1 or 1 indicate a strong relationship.
  - Those closer to 0 indicate a weak relationship.
  - 0 indicates no relationship. 
- **Correlation heatmaps** help you visualize this information


## Data Cleaning
``` Better data beats fancier algorithms. ```
- The first step to data cleaning is removing unwanted observations from your dataset. This includes duplicate or irrelevant observations.
  - **Structural errors** are those that arise during measurement, data transfer, or other types of "poor housekeeping."
  - typos or inconsistent capitalization
  - check for mislabeled classes

- Filter Unwanted Outliers
  - if you have a legitimate reason to remove an outlier, it will help your model’s performance.
  - outliers are innocent until proven guilty
- Handle Missing Data
  - you cannot simply ignore missing values in your dataset.
    -  the 2 most commonly recommended ways of dealing with missing data actually suck. They are:
      - Dropping observations that have missing values
      - Imputing the missing values based on other observations
  - Missing categorical data : The best way to handle missing data for categorical features is to simply label them as ’Missing’!
  - Missing numeric data For missing numeric data, you should flag and fill the values.
## Feature Engineering
Feature engineering is about creating new input features from your existing ones.
- Infuse Domain Knowledge
  - You can often engineer informative features by tapping into your (or others’) expertise about the domain.
- Create Interaction Features
  - The first of these heuristics is checking to see if you can create any interaction features that make sense. These are combinations of two or more features.
- Combine Sparse Classes 
  - Sparse classes (in categorical features) are those that have very few total observations.
- Add Dummy Variables:
  - Dummy variables are a set of binary (0 or 1) variables that each represent a single class from a categorical feature.
- Remove Unused Features :
  - Unused features are those that don’t make sense to pass into our machine learning algorithms.
  - Redundant features would typically be those that have been replaced by other features that you’ve added during feature engineering.
  - After completing Data Cleaning and Feature Engineering, you'll have transformed your raw dataset into an **analytical base table (ABT)**.
  - The key is choosing machine learning algorithms that can automatically select the best features among many options (built-in feature selection).
  - This will allow you to avoid overfitting your model despite providing many input features.
## Algorithm Selection
### Linear Regression 
- simple linear regression suffers from two major flaws:
  - It's prone to overfit with many input features.
  - It cannot easily express non-linear relationships
### Regularization in Machine Learning
- "advanced" tactic for improving model performance.
- Regularization is a technique used to prevent overfitting by artificially penalizing model coefficients.
- The first flaw of linear models is that they are prone to be overfit with many input features.
- Each coefficient would simply memorize one observation
- It can also remove features entirely
- It can discourage large coefficients
- The "strength" of the penalty is tunable
### Regularized Regression Algos 
- we’ve just seen 3 algorithms that can protect linear regression from overfitting:
1. Lasso Regression
2. Ridge Regression
3. Elastic-Net

- solve th e other problem It cannot easily express non-linear relationships
  - Decision Tree Algos
    - Decision trees model data as a "tree" of hierarchical branches. They make branches until they reach "leaves" that represent predictions.Due to their branching structure, decision trees can easily model nonlinear relationships.
    - As a result, individual unconstrained decision trees are very prone to being overfit.
### Tree Ensembles
- Ensembles are machine learning methods for combining predictions from multiple separate models. There are a few different methods for ensembling, but the two most common are:
  - Bagging attempts to reduce the chance overfitting complex models.
  - Boosting attempts to improve the predictive flexibility of simple models.
- Random forests :Random forests train a large number of "strong" decision trees and combine their predictions through bagging.

In addition, there are two sources of "randomness" for random forests:
  - Each tree is only allowed to choose from a random subset of features to split on (leading to feature selection).
  - Each tree is only trained on a random subset of observations (a process called resampling).

- Boosted trees : Boosted trees train a sequence of "weak", constrained decision trees and combine their predictions through boosting.
  - Each tree is allowed a maximum depth, which should be tuned.
  - Each tree in the sequence tries to correct the prediction errors of the one before it.


- The most effective algorithms typically offer a combination of regularization, automatic feature selection, ability to express nonlinear relationships, and/or ensembling. Those algorithms include:

  - Lasso regression
  - Ridge regression
  - Elastic-Net
  - Random forest
  - Boosted tree

## Model Training

### Split Dataset
- You can spend some of it to train your model (i.e. feed it to the algorithm).
- You can spend some of it to evaluate (test) your model.

- If you evaluate your model on the same data you used to train it, your model could be very overfit and you wouldn’t even know! A model should be judged on its ability to predict new, unseen data.
- Training sets are used to fit and tune your models. Test sets are put aside as "unseen" data to evaluate your models.
- Comparing test vs. training performance allows us to avoid overfitting... If the model performs very well on the training data but poorly on the test data, then it’s overfit.

### What are Hyperparameters?
- The key distinction is that model parameters can be learned directly from the training data while hyperparameters cannot
- There are two types of parameters in machine learning algorithms:
  - model parameters :Model parameters are learned attributes that define individual models.
    - They can be learned directly from the training data
  - hyperparameters : Hyperparameters express "higher-level" structural settings for algorithms.
    - They are decided before fitting the model because they can't be learned from the data

### What is Cross-Validation?
- Cross-validation is a method for getting a reliable estimate of model performance using only your training data.
- There are several ways to cross-validate. The most common one, 10-fold cross-validation
- These are the steps for 10-fold cross-validation:
1. Split your data into 10 equal parts, or "folds".
2. Train your model on 9 folds (e.g. the first 9 folds).
3. Evaluate it on the 1 remaining "hold-out" fold.
4. Perform steps (2) and (3) 10 times, each time holding out a different fold.
5. Average the performance across all 10 hold-out folds.

- also called your cross-validated score. 

### Fit and Tune Models :
- all we need to do is perform the entire cross-validation loop detailed above on each set of hyperparameter values we'd like to try.
- For **regression tasks**, we recommend **Mean Squared Error (MSE)** or **Mean Absolute Error (MAE)**
- For **classification tasks**, we recommend **Area Under ROC Curve (AUROC)**. (Higher values are better)

- The process is very straightforward:
  - For each of your models, make predictions on your test set.
  - Calculate performance metrics using those predictions and the "ground truth" target variable from the test set.










