# Text Classification (NLP) Project


## Project Overview
The goal of this project is to build a predictive machine learning model utilizing Natural Language Processing or NLP to classify text. My intention is to show my understanding of the iterative modeling process, final model selection and evaluation, and knowledge / application of NLP.

## Business & Data Understanding
I chose [this dataset](https://data.world/crowdflower/brands-and-product-emotions), provided by Crowdflower (now Appen.com). The set contains data on approximately 9000 Tweets and classifies their relationship with their content as Positive, Negative, or Neutral. The data has 3 features we can use for prediction, one being unfiltered text of the tweets themselves.

I am assuming the position of a data scientist hired by Twitter (now 'X'). Twitter wants to know if it is possible to utilize machine learning and NLP to predict the sentiment of a tweet based on its content. I built a multi-class classification model to help them make this determination.

## Modeling

I cleaned the data before the modeling process, altering some features and dropping others.

For a baseline, I created a dummy model that gave me stats to improve upon with other models. This model achieved a 60% accuracy score on testing data.

In pre-processing, I converted the text to lowercase, stripped the words, and removed punctuation.  Then, I removed stopwords, i.e. a pre-made list of unneccesary words for classification of text. After that, I Lemmatized the text using WordNetLemmatizer, mapping ntlk tags as well as tokenizing each tweet afterward.  The final result was a new column in the dataframe of just the preprocessed text.

After iterating through a few varieties of models, I landed on Logistic Regression for further improvement.

The first model proved difficult to improve on given few parameters to tweak with an NLP project, however I was able to slightly. After attempting to improve the model as much as possible by hand, I utilized a GridSearch to find the best parameters to train/test the data with. In doing so I improved the testing accuracy to 89% as well as 65% training accuracy/recall/precision.  There is still room for improvement in the recall of Negative tweets, however Neutral and Positive Tweets have decent recall as it stands.  Below are the classification reports for the initial Logistic Regression model as well as the GridSearch improved model.


![Report](images/base_logreg_stats.jpg)
![Report](images/gs_logreg_stats.jpg)


## Evaluation & Conclusion
My final recommendation is to use the Logistic Regression with Grid Search.

The Grid Search model has the highest accuracy when applied to the testing data and will lead to the most efficient use of resources. In other words, if Twitter is trying to predict the sentiment of tweets based on their content, the Grid Search model will be the least likely to point them to false positives (Negative tweets classified as Positive), which would result in a waste of resources.

If time allows, I would recommend also attempting to tune a Random Forests Model with a GridSearch as further improvement may be found there.

### Final Notebook
[Notebook](https://github.com/Wingaero/NLP_Project/blob/main/jupyter_notebook.ipynb)


## Contributers
Mason Walter <a href = "https://github.com/Wingaero"><img src='https://cdn.pixabay.com/photo/2022/01/30/13/33/github-6980894_1280.png' width = '25' height='25'></a><a href="www.linkedin.com/in/mason-c-walter/"><img src='https://upload.wikimedia.org/wikipedia/commons/8/81/LinkedIn_icon.svg' width = '25' height='25'></a>  

