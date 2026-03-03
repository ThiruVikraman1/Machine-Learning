**Machine Learning Regression**

Welcome to my Machine Learning repository! This repository contains a collection of Machine Learning projects, from basic regression models to predictive analytics. Each project includes data cleaning, model training, evaluation, and a deployment script.

**Repository Structure**

**1. Simple_Linear_Regression/: Predicting employee salary based on years of experience.**

   Salary_Data.csv # Dataset  
   Model_Creation.ipynb # Training and evaluation  
   Salary_Model.sav # Saved Pickle model  
   Deployment.ipynb # User input interface  

**2. Multiple_Linear_Regression/: Predicting startup profit based on R&D, administration, and marketing expenses.**

   50_Startups.csv # Multi-feature dataset  
   Model_Creation.ipynb # Training and one-hot encoding  
   Profit_Model.sav # Saved Pickle model  
   Deployment.ipynb # Real-time prediction  

**3. Support_Vector_Machine/: Predicting startup profit based on R&D, administration, and marketing expenses.**

   50_Startups.csv # Multi-feature dataset  
   Model_Creation.ipynb # Training and hyperparameter tuning  
   Profit_Model.sav # Saved Pickle model  
   Deployment.ipynb # Real-time prediction  

**4. Decision_Tree/: Predicting startup profit based on R&D, administration, and marketing expenses.**

   50_Startups.csv # Multi-feature dataset  
   Model_Creation.ipynb # Data cleaning, training, and R-squared evaluation  
   Profit_Model.sav # Saved Pickle model  
   Deployment.ipynb # Real-time prediction  

**5. Random_Forest/: Predicting startup profit based on R&D, administration, and marketing expenses.**

   50_Startups.csv # Multi-feature dataset  
   Model_Creation.ipynb # Data cleaning and grid of 24 experiments  
   Profit_Model.sav # Final model exported via pickle  
   Deployment.ipynb # End user script for real-time prediction  

**Projects Overview**

**Project 1: Simple Linear Regression**

Objective: Establish a linear relationship between one variable (years of experience) and another (salary).

Result: Achieved high accuracy with a clear best-fit line.

**Project 2: Multiple Linear Regression (Startup Profit)**

Objective: Predict the profit of 50 startups using R&D, administration, and marketing expenses.

Categories: Used one-hot encoding for the "State" column. I set drop_first=True to prevent the dummy variable trap.

Evaluation: Achieved an R-squared of 0.93. I used adjusted R-squared to ensure that added features, like State, genuinely contribute to the model.

**Project 3: Support Vector Regression (SVR)**

Model Performance: Achieved 93% accuracy, the same as multiple linear regression.

Hyperparameter Tuning: Set the C parameter to 0.01 to create a soft margin. This reduced overfitting and helped the model focus on the overall trend in the startup data.

Kernel Analysis: I tested RBF and polynomial kernels. However, the strictly linear nature of the 50_Startups dataset made the linear kernel most effective.

**Project 4: Decision Tree Regression (DTR)**

Model Performance: Achieved a peak accuracy of 95.8% (R² score), outperforming both multiple linear regression (93%) and SVR (93%).

Hyperparameter Tuning: Conducted extensive tuning of the criterion and splitter parameters. Using absolute_error as the criterion was most effective, as it is more robust to outliers and focused on the median profit of startup groups rather than the mean.

Structural Insight: Visualizing the tree confirmed that R&D spend was chosen as the root node, marking it as the most important predictor of a startup's profit.

Non-Linear Flexibility: While SVR struggled with non-linear kernels like RBF, the decision tree’s ability to split the data into distinct segments allowed it to capture patterns that linear models missed.

**Project 5: Random Forest Regression (RFR)**

Model Performance: Achieved a peak accuracy of 83.4% (R² score). While the single decision tree had a higher peak of 95.8% for this dataset, the random forest showed greater stability by averaging the predictions of multiple trees.

Hyperparameter Tuning: Conducted a grid search across 24 combinations of n_estimators, criterion, and max_features. The best setup was found using 50 trees (n_estimators=50) with the squared_error criterion.

Feature Diversification: Using max_features='log2' proved effective. The model reduced the influence of any single feature and improved overall generalization.

Project Conclusion: Final Model Comparison

After implementing and tuning four major regression algorithms, I evaluated their performance based on the R² score to find the best model for predicting startup profit.

Performance Leaderboard

Best Model Configuration | R² Score  
--------------------------|----------  
Absolute Error (DTR) Splitter: Best | 0.95 (95%)  
Multiple Linear Regression Default | 0.93 (93%)  
Support Vector Machine (SVR) | Kernel: Linear, C: 0.01 | 0.93 (93%)  
Random Forest | n_estimators: 10/50, max_features: sqrt/log2 | 0.83 (83%)  
