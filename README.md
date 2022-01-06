# Income classification
Link to Heroku Server: https://income-prediction-1.herokuapp.com/

## Running the Application
1. Clone repository to your local machine.
2. Open Terminal/Git Bash
3. Navigate to folder which contains application (folder with app.py file)
4. Activate your python environment (conda activate PythonData or similar)
5. Run the application from your command line (python app.py)
6. Terminal/Git Bash will show * Running on http://127.0.0.1:5000/. Copy the url end point and paste into your browser window.

## Project Overview
The purpose of this project is to predict if one’s income is more or less than 50K based on 10 given features. We used income classification dataset found on Kaggle.com. The dataset has 14 attributes and 1 target, we dropped and cleaned the data and remained 30162 rows of data and 10 features for our machine learning model.

To determine which machine learning model to use in prediction, we were applying three different machine learning models including support vector machines (SVMs), logistical regression and random forest and choosing one with the best performance for our model.

## Data
- Data source: https://www.kaggle.com/lodetomasi1995/income-classification

  The Data Source contains information on age, workclass, final weight (total number of people represented in row), education level, marital status, occupation, familial relationship, race, gender, capital gain, capital loss, hours worked per week, and native country.
- Database Engine: PostgresSQL
- Tables: Income_Table


## Machine Learning

### Data-processing
1.	Find and drop total of 2399 missing data. Remaining 30162 rows of data for our machine learning model.
2.	Drop unnecessary columns: "fnlwgt", "education-num", "capital-gain", "capital-loss".
3.	Using `One-Hot Encoding` to fit and transform categorical variables.
4.	Using `StandardScaler` module standardizes the data so that the mean of each feature is 0 and standard deviation is 1.

### Features used in the model
- Age: Current age (in years)
- Workclass: Employment status of an individual (e.g.	Private)
- Education: Highest degree obtained (e.g. HS-grad, Bachelors)
- Marital-status: Marital status of an individual (e.g. Divorced, Married-AF-spouse)
- Occupation: Industry/role employed in (e.g. Exec-managerial, Craft-repair)
- Relationship: Represents what this individual is relative to others(e.g. Husband, Wife)
- Race: Descriptions of an individual’s race (e.g. White, Black)
- Sex: Gender assigned at birth (Male/Female)
- Hours-per-week: Weekly hours employed (e.g. 40)
- Native-country: Country of origin for an individual

### Training and testing dataset
Using Scikit-learn's `train_test_split` module to split 75% of features (X) and target (y) data into training data and 25% for testing data.

### Machine Learning Models
In our analysis, the outcome of income prediction is a binary classification (>50K or <=50K). Here are the results of three different machine learning models which are commonly used in categorizing sample into groups.

Run our models with the same train test split, comparison the balanced accuracy score and precision, result as below:

 Models               |Balanced accuracy score   |Precision      |
 ---------------------|------------------------- |-------------- |
 SVM                  |0.7478                    |0.8372         |
 Logistic Regression  |0.7534                    |0.8396         |
 Random Forest        |0.74                      |0.81           |
 
Our best scores are with Logistic Regression with a balanced accuracy score of 0.75 and precision of 0.84.

## Dashboard

#### Interactive elements

The webpage includes input boxes for users to provide the necessary information for our model to run a prediction as well as additional tabs which provides the user insight into:
- The methodology into which machine learning models were tested, which model was selected to make predictions, and the rationale behind our selection.
- Additional data insights into the relationship between the features and model predictions.

#### Tools/technologies for the creating the dashboard

Programming Languages: Javascript, Python, HTML

Tools: Flask, Tableau

- Running python script to grab inputs from web entry running ML model (logistic regression) to predict income level based on input, with output showing whether user is likely to have income above or below $50K per year. Additional pages with deeper analysis and background, as described in interactive elements.

- Tableau public: Summarizing trends in dataset among features used.

