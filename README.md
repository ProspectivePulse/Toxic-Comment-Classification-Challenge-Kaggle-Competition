# Toxic Comment Classification Challenge

"Discussing things you care about can be difficult. The threat of abuse and harassment online means that many people stop expressing themselves and give up on seeking different opinions. Platforms struggle to effectively facilitate conversations, leading many communities to limit or completely shut down user comments.

The Conversation AI team, a research initiative founded by Jigsaw and Google (both a part of Alphabet) are working on tools to help improve online conversation. One area of focus is the study of negative online behaviors, like toxic comments (i.e. comments that are rude, disrespectful or otherwise likely to make someone leave a discussion). So far they’ve built a range of publicly available models served through the Perspective API, including toxicity. But the current models still make errors, and they don’t allow users to select which types of toxicity they’re interested in finding (e.g. some platforms may be fine with profanity, but not with other types of toxic content)."

Disclaimer: the dataset for this competition contains text that may be considered profane, vulgar, or offensive."

Source: https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge


## Project Background and Scope


### Problem Statement

Determine the probability of different types of toxicity of comments from Wikipedia edits.

This is a multi-label classification problem whereby each comment can belong to one or more class at the same time. 

Being able to successfully predict the toxicity class of a comment can have immense benefits across the board for social media apps and can be a vital step towards keeping online discussions civil.

The quality of predictions will be a function of the features/predictor variables which will be engineered from the pool of comments supplied.

### Datasets

The data has been made available via the following url - https://www.kaggle.com/c/jigsaw-toxic-comment-classification-challenge/data

The datasets provided contains a large number of Wikipedia comments which have been labeled by human raters for toxic behavior. The types of toxicity are:

•	toxic
•	severe_toxic
•	obscene
•	threat
•	insult
•	identity_hate

### File Descriptions

•	train.csv – Contains the training data with the comments and their binary labels
•	test.csv – Contains data for which comment toxicity probabilities need to be predicted
•	sample_submission.csv - a sample submission file in the correct format


### Previous Research
So far a range of publicly available models served through the Perspective API have been built, which also includes toxicity. However, the current models still make errors, and they don’t allow users to select which types of toxicity they’re interested in finding (e.g. some platforms may be fine with profanity, but not with other types of toxic content).
https://github.com/conversationai/unintended-ml-bias-analysis

 
### Project Concern

Incorrect comment classification is the primary concern while building the predictive model as in a real world scenario this may lead to inappropriately blocking a comment stream which may have been classified as toxic or obscene etc. in error.  

NB: The underlying assumption is that comments in the training data set provided have been accurately classified and afford sufficient coverage for building a generalisable model. 

### Approach

The proposed method involves two stages
1.	Embed comments in a fixed dimensionality vector space
2.	Model each type of toxicity in order to be able to assign membership probability to future comments
Embedding comments
The proposed approach is to use doc2vec to embed comments in an N-dimensional vector space, using the training data to learn the model. Experiments and analysis of resulting vector will be required to assess the quality of the embeddings as well as determine the best value of N (this may further require a full pipeline analysis).

### Modelling Toxicity

The proposed approach is to use the vector representations of comments to model the individual toxicity types. Experimental evaluation is required to determine if a multi-classifier setup will be used or a single classifier with class probabilities.

#### Outcomes
The planned approach for building the model is two-fold as mentioned above – 
1. Embedding Comments, 
2. Modelling toxicity

The higher the predictive accuracy (lower MSE or higher ROC AUC score) of the model as ratified through test approaches such as cross-validation and regularisation on a subset of the training data set will provide an indication of the degree of “predictive success” of the model.

