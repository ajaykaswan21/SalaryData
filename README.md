# SalaryData-attritionJob Salaries Estimator for Different Data Science Positions

Designed a tool that estimates job salaries to help data scientists negotiate their income when they are applying for different data science jobs.
Scraped the job descriptions from glassdoor.com using python and selenium
Developed Linear, Lasso, and Random Forest Regressors using GridsearchCV to get the best model.
Deployed the Machine Learning model in Heroku using flask

Web Scraping

Used the web scraper github repo (above) to scrape the job postings from glassdoor.com. With each job, we obatin the following:

Job Title
Salary Estimate
Job Description
Rating
Company Name
Location
Headquarters
Size
Founded
Type of Ownernship
Industry
Sector
Revenue
Competitors
After scraping the data I needed to clean it so that it can be usable for our model. I made the following modifications and created the following variables:

Parsed only the numeric data out of Salary
Made seperate columns for employer provided salary and hourly wages
Salary column contained few empty values so removed the rows without Salary
Parsed rating out of company text
Made a seperate column for the Company State
Made a new column to check if the job is at the company’s headquarters
Added a new column age of company by using the founded date
Added columns to check if the different skills were listed in the job description:
Made a new column for simplified job title and Seniority
Made a new column for description length
Python
Exploratory Data Analysis

EDA plays a very important role at this stage as the summarizat
ion of clean data helps in identifying the structure, outliers, anomalies, and patterns in data. I looked at the distributions of the data and the value counts for the various categorical variables. Have done the univariate, bivariate analysis, and plotted histograms,boxplots,bar graphs,pivot tables etc. to represent the data.
Model Building

First, I modified all the categorical variables into dummy variables. Then I splited the data into training and test sets with a test size of 20%. I tried three different models and evaluated them using Mean Absolute Error. I chose MAE because it is kind off easy to interpret and outliers aren’t particularly bad in for this type of model.

Multiple Linear Regression: Base Model
Lasso Regression: As there are any 0s and 1s(because of the sparse data from the many categorical variables), I have chosen a normalized regression like Lasso and thought it would be effective.
Random Forest Regression – With the sparsity associated with the data, I thought that this would be a good fit for our data.
Model Performance

The Random Forest model perfored better than the other models on the test set.

