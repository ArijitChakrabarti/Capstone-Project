# Capstone Project Team 1013

Hi!  This is my project towards my Post Graduate Certification in Data Science.  The files uploaded included the data files that were downloaded SQL from INSAID's repository towards this project, data cleaning, exploratory data analytics (on two of the features assigned) & and the model itself.  I have dabbled with AutoML as well using Pycaret.


# Files

The CSV files i.e. **department_data.csv, employee_data.csv & employee_details_data.csv** were downloaded through SQL.  The csv files are the output from the ipynb file For **downloading data.ipynb**, which will be automatically created once the notebook file is run on python.

Then basis subsequent meetings with the team - the data was cleansed using the steps outlined in the notebook file **data cleaning.ipynb** - which results in the file **clean_data.csv**.

The **clean_data.csv** is then used to perform EDA which is done in using the file **EDA on last eval and n proj.ipynb** & model building using Pycaret in file **Pycaret.ipynb** and **Model Building and Analysis.ipynb**  

## Way foward

Subsequent steps are pending, including closure on the final model that we are to use. The current model developed by me has an AUC value of .95, the following is a plot of the same:
![AUC ROC Curve](https://github.com/ArijitChakrabarti/Capstone-Project/blob/main/AUCROCCURVE.PNG?raw=true)

## Few Key Takeouts

I performend model building across multiple models details of  which are outlined below for reference, details summarised from **Model Building and Analysis.ipynb** file.  Since the dataset was imbalanced I decided  to use **SMOTE** - Synthetic Minority Oversampling Technique to balance out the dataset.  However the out-put has been interesting to say the least.

|Model           |F1 Score Accuracy	             |Weighted Avg F1 score  | Remarks 	|
|----------------|-------------------------------|-----------------------------|--|
|Logistic Regression|0.80           |0.78           | Good Initial
|LR with SMOTE        |0.60	            |0.78            | Accuracy dropped, convergence failed|
|Gaussian NB         |0.80|0.81| Improvement weighted F1|
|Gaussian NB with SMOTE| 0.51 | 0.52 | Decline on both counts |
|SGD Classifier| 0.76 | 0.66 | Not a good score|
|SGD with SMOTE| 0.76 | 0.78 | Improves weighted F1 score though not significantly|
|K Neighbors Classifier | 0.89 | 0.89 | Best yet!
|K Neighbors with SMOTE | 0.85 | 0.86 | No improvement with SMOTE
|Decision Tree Classifier | 0.96 | 0.96 | Saves the day each time!
|DT with SMOTE | 0.96 | 0.96 | No improvement with SMOTE - F1 scores remain same
|Random Forest Classifier | 0.98 | 0.98 | Even Better!
|RFC with SMOTE | 0.98 | 0.98 | No improvement with SMOTE
|Support Vector Machines Classifier | 0.79 | 0.72 | Average performance
|SVC with SMOTE | 0.72 | 0.74 | Performance drop with SMOTE

Hence basis the above I took the RFC model - which performed the best and tuned the same using GridSearch to arrive at the AUC ROC score mentioned in the above segment.

## Project Submission

The Submission itself is to be done basis the column headers in **model_evaluation_table.csv** & **model_evaluation_results.csv**
