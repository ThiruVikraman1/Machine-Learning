**🚀 Machine Learning Projects**

Welcome to my Machine Learning repository! This repository contains a collection of Machine Learning projects, ranging from fundamental regression models to advanced predictive analytics. Each project includes data preprocessing, model training, evaluation, and a deployment script.

**📁 Repository Structure**

**1.Simple_Linear_Regression/: Predicting Employee Salary based on Years of Experience.**

* Salary_Data.csv           # Dataset
* Model_Creation.ipynb      # Training & Evaluation
* Salary_Model.sav          # Saved Pickle Model
* Deployment.ipynb          # User Input Interface

**2.Multiple_Linear_Regression/: Predicting Startup Profit based on R&D, Administration, and Marketing expenditures.**

* 50_Startups.csv           # Multi-feature Dataset
* Model_Creation.ipynb      # Training & One-Hot Encoding
* Profit_Model.sav          # Saved Pickle Model
* Deployment.ipynb          # Real-time Prediction

**3.Support_Vector_Machine/: Predicting Startup Profit based on R&D, Administration, and Marketing expenditures.**

* 50_Startups.csv            # Multi-feature Dataset
* Model_Creation.ipynb       # Training & Hyper Parameter tuning
* Profit_Model.sav           # Saved Pickle Model
* Deployment.ipynb           # Real-time Prediction


**4.Decision_Tree/: Predicting Startup Profit based on R&D, Administration, and Marketing expenditures.**

* 50_Startups.csv            # Multi-feature Dataset
* Model_Creation.ipynb       # Data preprocessing, training and R-sqaure evaluation
* Profit_Model.sav           # Saved Pickle Model
* Deployment.ipynb           # Real-time Prediction

**5.Random_Forest/: Predicting Startup Profit based on R&D, Administration, and Marketing expenditures.**

* 50_Startups.csv            # Multi-feature Dataset
* Model_Creation.ipynb       # Data preprocessing and grid of 24 experiments
* Profit_Model.sav           # Finalized model exported via pickle
* Deployment.ipynb           # End user script for real-time Prediction

**📊 2. Projects Overview**

**Project 1: Simple Linear Regression**

**Objective:** To establish a linear relationship between a single independent variable (Years of Experience) and a dependent variable (Salary).

**Result:** Achieved high accuracy with a clear "Best Fit Line."

**Project 2: Multiple Linear Regression (Startup Profit)**

**Objective:** Predict the profit of 50 startups using R&D, Administration, and Marketing expenditures.Handling 

**Categories:** Implemented One-Hot Encoding for the "State" column. Used drop_first=True to avoid the Dummy Variable Trap.

**Evaluation:** Achieved an **R squared of 0.93**. I use Adjusted R-squared to ensure added features (like State) truly contribute to the model.

**Project 3: Support Vector Regression (SVR)**

**Model Performance:** Achieved **93% Accuracy** same as  Multiple Linear Regression (93%).

**Hyperparameter Tuning:** Tuned the $C$ parameter to 0.01 to create a "Soft Margin," which reduced overfitting and allowed the model to focus on the global trend of the startup data.

**Kernel Analysis:** Tested RBF and Polynomial kernels; however, due to the strictly linear nature of the 50_Startups dataset, the Linear Kernel proved most effective.

**Project 4: Decision Tree Regression (DTR)**

**Model Performance:** Achieved a peak accuracy of **95.8%** ($R^2$ Score), officially outperforming both Multiple Linear Regression (93%) and SVR (93%).

**Hyperparameter Tuning:** Conducted extensive "hypertuning" of the criterion and splitter parameters. Using absolute_error as the criterion proved most effective, as it is more robust to outliers and focused on the median profit of startup groups rather than the mean.

**Structural Insight:** By visualizing the tree, it was confirmed that R&D Spend was selected as the Root Node, identifying it as the single most important predictor of a startup's profit.

**Non-Linear Flexibility:** While SVR struggled with non-linear kernels like RBF, the Decision Tree’s ability to "split" the data into distinct segments allowed it to capture local patterns that linear models missed.

**Project 5: Random Forest Regression (RFR)**

**Model Performance**: Achieved a peak accuracy of **83.4%** ($R^2$ Score). While the single Decision Tree reached a higher peak of 95.8% for this specific dataset, the Random Forest demonstrated greater stability by averaging the predictions of multiple trees.

**Hyperparameter Tuning**: Conducted a grid search across **24 unique combinations** of `n_estimators`, `criterion`, and `max_features`. The optimal configuration was found using **50 trees** (`n_estimators=50`) and the **`squared_error`** criterion.

**Feature Diversification**: Implementing **`max_features='log2'`** proved highly effective. The model reduced the dominance of any single feature and improved the forest's overall generalization.

**🏆 Project Conclusion:**
Final Model ComparisonAfter implementing and tuning four major regression algorithms, I have evaluated their performance based on the $R^2$ Score to identify the most effective model for predicting startup profit.

**📊 Performance Leaderboard**
**Best Model**                 **ConfigurationR2**                                 **$R^2$ Score**

Absolute Error(DTR)               Splitter:                                         Best0.95 (95%)

Multiple Linear Regression        Default                                           0.93 (93%)

Support Vector Machine (SVR)      Kernel: Linear, C: 0.01                           0.93 (93%)

Random Forest                     n_estimators: 10/50, max_features: sqrt/log2      0.83 (83%)
