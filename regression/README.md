# Project Overview
## 1. Predicting the sale price of Bulldozers  (regression problem)
---

### 📝 About the Project  
In this project, the bulldozers past sales prices are used to predict the sale price of future bulldozers based on their characteristics.
- Inputs: Bulldozer characteristics such as make year, base model, model series, state of sale (e.g. which US state was it sold in), drive system and more.
- Outputs: Bulldozer sale price (in USD).
This is a typical regression problem since we need to predict a numerical value. And since we're predicting results with a time component (predicting future sales based on past sales), this is also known as a *time series* or *forecasting* problem.
---

### ✨ Notebook logic
We will go through the 6-step Machine Learning model framework in the [notebook](https://github.com/emmanguyen102/Machine-Learning-portfolio/blob/main/regression/Random_forest_regression_problem.ipynb)
![Screenshot 2025-01-15 at 14 00 25](https://github.com/user-attachments/assets/e506b7d9-162b-4265-aecb-6efa040ab20d)

1. Identify the problem:
We are trying to answer the question: How well can we predict future sale price of a bulldozer, based on past sale points and bulldozer characteristics?

2. Dataset: The dataset can be found [License]([#license](https://www.kaggle.com/c/bluebook-for-bulldozers/data)). Data is split into three parts:

- **Train.csv**: is the training set, which contains data through the end of 2011.
- **Valid.csv**: is the validation set, which contains data from January 1, 2012 - April 30, 2012.
- **Test.csv**: It contains data from May 1, 2012 - November 2012.

The key fields are in **train.csv** are:

- SalesID: the uniue identifier of the sale
- MachineID: the unique identifier of a machine.  A machine can be sold multiple times
- saleprice: what the machine sold for at auction (only provided in train.csv)
- saledate: the date of the sale

These datasets are raw data so that explanatory data analysis and data manipulation is needed before model training.

3. Evaluation:
The evaluation metric is root mean squared log error (RMSLE). As with many regression evaluations, the goal is to get this value as low as possible. This evaluation metric is not defined in any sklearn library, ended up creating own function to get this metric. 

4. Features:
The [following data dictionary](https://docs.google.com/spreadsheets/d/18ly-bLR8sbDJLITkWG7ozKm8l3RyieQ2Fpgix-beSYI/edit?gid=1021421956#gid=1021421956) which contains information about what each attribute of the dataset means.

6. Modelling:
Model chosen is Random Forest Regression. 

8. Experiments:
- Training model on smaller subset of data.
- Tuning hyperparameters to get the best fit parameters to train the model. 

---

### 🚀 Key findings:
- Choosing reasonably feasible model to train the given dataset.
- Training on smaller dataset for experimentation.
- Data pre-processing in a given udf instead of repeating the whole process for different datasets.
- Splitting into validation and training datasets.
- Tuning hypermeters to find the most idealistic model to train the dataset.
- Creating own model evaluation metric and get its best result by experimenting.



