# Project-4-Web-Scraping-Job-Postings

EXECUTIVE SUMMARY
-------------
Data Science is a rapid expanding field and the market demand potential candidates with suitable skill set. This project is aimed to look at the various factors that influences the salaries across various Data related jobs. The project was an open-ended project where we had few objectives for the study. 

**Objectives:**

1. Obtain data from aggregators via web scraping. Perform Data Cleaning and bring the data in a format so that we can use them as features.
2. To predict salary, by using either a classification or regression model by using features like the location, title, and summary of the job.
3. Using the job postings identify features in the data related to job postings that can distinguish job titles from each other.

**Approach:**

Data was collected from the job aggregator site seek.com. Fom all over Australia, scraped five different job titles namely :
1. Data Scientist
2. Data Analyst
3. Data Engineer
4. Machine Learning 
5. Business Intelligence 

The scraping was done using python library Beautiful soup and requests. 
I extracted 1247 unique job postings for nine different features job title, job location, job area, company, job classification, job description, job type. I used ‘for’ loop to parse over the pages and further ‘if-else’ conditions were used to extract the text from corresponding tags accurately and consistently.The scrapped data was cleaned using library re and string. Salaries usually was expressed in a range, so I cleaned the salary column and found the mean of the salary range and used that as my estimated salary. 

**Task 1:**

To predict the salary this problem was approached using regression and classification. The first was to construct a linear model to predict median salary based on our extracted features. The second was to classify job listings into low (<90000 AUD p.a.) medium (between 90000 and 125000 AUD p.a.) and high (> 125000 AUD p.a.) salaries and build a classification model to predict what salary class a given job will fall into. From this we can determine the features that have the greatest impact on salary.

**Task 2:**

The other task was to predict the job title based on the description provided. For this I had to carry out Natural Language Processing (NLP) analysis. I used sklearn library’s Countvectorizer and Tfidfvectorizer functions. This converts words in the text into vectors. The next step I did was put the vectorized data into a classification algorithm and get results for both the vectorizer. 

**Findings:**
1. I constructed a linear model to estimate median salary, simple linear regression had a negative score that means my model did worse than average. 
2. Secondly,I used linear regression with regularization, but none gave good results. Then I used GridsearchCV with Logistic Regression, Decision tree, Random forest and SVM. 
3. The classification models performed well with 86% accuracy achieved by the SVM approximately 36% better than the baseline. 4. The top features that have the biggest influence in the predicting salary was job title, job work type and area of the job post.
5. For predicting the job title from the job description, the results of Countvectorizer and tfidfvectorizer were put in classification models multinomial naïve bayes, Logistic Regression and random forest. I found the results Countvectorizer had good scores over tfidf vectorizer.
6.The random forest with countvectorizer was able to classify different job roles with 66% accuracy, approximately 15% better than baseline. This model found few top skills important for various job types. The results were not very good, because there is lots of overlapping between the various data related jobs.

**Conclusions:**

Our modelling suggests that important factors to for salary prediction is the job role and the work type. I also found that there are few skills one should know in order to enter data related positions like python, spark, azure, machine learning modelling etc.
