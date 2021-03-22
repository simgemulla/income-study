# income-study

Technical Specifications:

In this project I used;
Numpy, Pandas for getting, cleaning and manipulating data.
Matplotlib for plotting and visualization of data.
Scikit-learn for the model. I used logistic regression because it is simple to use and based on my research it can usually be used for classification problems. In this problem, we are trying to find out that whether the income of the customer is more than 50K or not for people whose salaries are unknown. This is a classification, so we can use it here.

Process Details:

First of all, I read the data from csv file based on semicolons. Based on the data on the table     there is total number of 45222 data, 11208 of them are having income more than 50K, and 28455 of them are less than or equal to 50K. 
Since we will get output from data, not NA or Null values, I dropped NA values from the data.
To see which columns have more unique values, I got value counts of all columns. Then I dropped all columns which more likely do not affect the income values. These are: 'hours-per-week' , 'capital-loss', 'capital-gain','age','native-country', ‘Name’.
I mapped the values of the income column with 1 and 0 values.
Then mapped all the remaining string values with integer values. (you can see data_mapping.xlsx file.)
I grouped every column one by one and took the mean of income. We can see the independent attributes against income. We can see the outputs from the graphics below.
For the model, I used Logistic Regression from scikit-learn. I converted income to dataframe, and the other attributes to another dataframe by concatenating them. After that, I split them    into random train and test subsets and performed train_test_split(df_income_x, df_income_y, test_size=0.33, random_state=42). (These values are based on default values/documentations).
Trained the model by training data, then I tried values with predict function. 
To see the accuracy, I got Accuracy: 0.780498318820588 by running;
 print("Accuracy:",metrics.accuracy_score(y_test, y_predict))
