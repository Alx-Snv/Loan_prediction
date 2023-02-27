# Loan prediction machine learning model deployment using flask
Hi! Welcome to this project that has been created for deploying a machine learning based website using flask for when entered the necessary details from the customers can predict whether they will be eligible for loan approval or not.
Loan lending is the backbone of every bank. Majority if not almost all of the banks revenue is generated from loans. To achieve maximum profits banks always ensure that their assets will be in safe hands. 
The process for applying for loans is a tedious one as it involves a thorough check of the applicant's background including their finances, family situation and also criminal records, etc. But even after all these steps it does not guarantee that the chosen applicant will be able to pay off his debt or not. This process usually requires a huge amount of time if done manually. Hence, i have tried to build a ML system which will predict the loan approval status and automate the whole process reducing the time consumed.
# Dataset
The data set here is the loan prediction from Kaggle.Dream Housing Finance company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have given a problem to identify the customers segments, those are eligible for loan amount so that they can specifically target these customers.
# EDA
The steps performed:
# 1. Data summary- 
Obtaining information about the data such as number of entries, column name and datatypes, presence of null data if any, statistical information such as count, mean, mode, etc. to get the general gist of the features present.
# 2. Data filling- 
There were data columns of both the categorical and the numerical containing null values. We have replaced all the null values with mode i.e. the values having maximum frequency in that particular column.
# 3. Data Visualization-
After cleaning the data, visualization have been performed using matplotlib and seaborn libraries. The data has been split into numerical and categorical dataframes for plotting graphs.
## Heatmap- 
The heatmap is useful for seeing how each feature interact with each other and how they impact the target feature(loan status). Few of the features influencing the output columns are applicant income, loan amount, loan term and credit history.
## Countplot and histogram- 
The numerical dataframe was utilized for creating histograms and the categorical datframe was used for creating countplots. They display how the data is distributed across the dataset in addition to checking for skewness in the data.
## Boxplot-
The main objective of boxplots is to detect outliers present in the dataset. It is necessary to remove them because they may impact the target feature negatively in the training phase of the model, thus skewing the final outcome.
# 4. Data Encoding-
The categorical dataframe consists of columns which have object datatype which will not be accepted by the ML algorithm. So we need to encode these columns by making use of encoding techniques. Label encoder is being implemented here because the number of categories is large.
# Data Modelling
After the EDA, next step is to concatenate the numerical and categorical dataframes into a single dataframe.
- We have the final datframe ready. Moving on, we import the ML libraries needed and split our data into training and tesing data. Assigning 75% of the data to training and remaining to testing.
- Declaring objects for the ML algorithms selected.
-Generating a model function to pass all the classification algorithms for fitting and prediciting over the dataset as well as providing the classification report, accuracy of said models.
-Fitting and testing the models with the help of the model function and generating classification reports depicting training and testing accuracy. The results are shown below-
## Decision tree- 68%
## Random Forest - 75%
## Logistic Regression - 78%
-These results were obtained without any tuning on the DT and RF classifiers. After performing Hyperparameter tuning the results of decision trees were boosted and rose upto ##79% which was the highest accuracy received in this process.
- We created a feature importance plot to depict the contribution of each feature towards the target outcome.
## This concluded the data model creation phase, we saved the model by using the pickle function.
# Deploymnet
For the deployment process, I choose to deploy it using flask framework and also created a simple html form. 
## HTML form-
The html form created here is one without any css or js scripts. It uses only the basic of html code to create a simple web application and is stored as a template. The form is linked with the app source code so that the data collected from the user gets sent to the app code.
The form contains text boxes to enter data manually and dropdown list for options where they are required.
The user then can send their detail to the python code by clicking on the submit button.
The result will be then displayed on the bottom of the web page.
## App file-
The flask framework is being used as this is just a development project. We start by creating a object app to create a flask instance, which is then used to run the application. Flask uses it to know from where to get resources, templates, static files, etc required to run the application.
Then we define the route for flask to get the html template, collect the data and send the data back to the python code to process the output.
Flask POST request is used  because that enables users to send HTML form data to server.
After the data is received, it gets processed by the predict function which then converts the data into an array which can be accepted by the ML model trained by us.
By using if and else statement we are able to give out the result in text form rather than binary 0 and 1 which may confuse the user if they are not familiar with boolean data types.
## This is the complete run-down of the project that has been created. Hope it is helpful for understanding the code better.
