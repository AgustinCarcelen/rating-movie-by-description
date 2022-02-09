# rating-movie-by-description
predict the rating of a movie based on its description using a logistic regression model by [Agustin](https://www.linkedin.com/in/agustin-carcelen-chicote-b70048231/)

## Table of content
- [Description](https://github.com/AgustinCarcelen/rating-movie-by-description/edit/blob/README.md#Description)
- [Pre requirements](https://github.com/AgustinCarcelen/rating-movie-by-description/edit/blob/README.md#Pre-requirements)
- [Process](https://github.com/AgustinCarcelen/rating-movie-by-description/edit/blob/README.md#Process)
- [Result](https://github.com/AgustinCarcelen/rating-movie-by-description/edit/blob/README.md#Result)
- [How to improve](https://github.com/AgustinCarcelen/rating-movie-by-description/blob/main/README.md#How-to-improve)

## Description
Our goal is to predict the rating of a movie based on its description.<br/>
To do this, we will apply a logistic regression model to our database.

## Pre requirements
To be able to execute the files correctly you will need to have installed:
- [Jupyter lab](https://jupyter.org/)

## Process
You can see the code for these steps [here](https://github.com/AgustinCarcelen/rating-movie-by-description/blob/3ebfddfa890853fc0587f90280da558c8547142b/RegresionModel.ipynb)

### Getting database
**Step 1:** We create a query to obtain the columns we need from the database.<br/>
**Step 2:** Create a new Jupyter notebook, establish a connection with the sakila database.<br/>
**Step 3:** Create a Python function to retrieve the data from the database given the engine from the previous query.

### Data processing and analysis
**Step 4:** In our database the movies are classified according to ['G','PG','PG-13','NC-17','R'] then we create a Python function named binary_rating which will replace the rating values by 'Yes' or 'No' whether the movie rating is in ['G','PG','PG-13'] or not (['NC-17','R']).<br/>
**Step 5:** Create a Python function name get_df_corpus that given the dataframe,will return a list in which each element will be a movie description. Store the function returned list as corpus for later.<br/>
**Step 6:** Do the data splitting (ie. set the X and the y).<br/>
**Step 7:** Do the train-test split.<br/>
**Step 8:** Now what you need to create a model will be to dummify the words appearing in each description (ignoring stop-words).

### Apply the logistic regression model
**Step 9:** Train a logistic regression model using X_train_tfidf and y_train as input.<br/>
**Step 10:** Get the rating predictions for the X_train_tfidf and X_test_tfidf.

### Save your model
**Step 11:** Use pickle to save: the vectorizer, the tf_transformer in a folder named transformers and the model a folder named models.

## Result
As a result we have a model that allows us to predict if the movie is good or not with a precision between 60%-65%.<br/> 
This may be because our database was too small or the descriptions were not detailed enough. But can we improve it?

## How to improve]
We can improve our model by applying different methods.<br/>
-Expand the sample in order to better train the model.<br/>
-Search for a description that provides us with more details of the movie.<br/>
-Scaling our numerical values to be able to train different regression models.
