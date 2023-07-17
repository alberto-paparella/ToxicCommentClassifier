# ToxicCommentClassifier

Discussing things you care about can be difficult. The threat of abuse and harassment online means that many people stop expressing themselves and give up on seeking different opinions. Platforms struggle to effectively facilitate conversations, leading many communities to limit or completely shut down user comments. This leads to the interest in building tools to help improve online conversation, one area of focus being the study of negative online behaviors, like toxic comments (i.e., comments that are rude, disrespectful or otherwise likely to make someone leave a discussion).

Hence, the aim of this project is to build a multi-headed model that’s capable of detecting different types of toxicity like threats, obscenity, insults, and identity-based hate. This model will hopefully help online discussion become more productive and respectful. In order to do so, different technologies have been evaluated on the mean column-wise ROC AUC (i.e., the score is the average of the individual AUCs of each predicted column). For each id in the test set, the model predicts a probability for each of the six possible types of comment toxicity (toxic, severetoxic, obscene, threat, insult, identityhate).

## Dataset

The dataset is comprised of a large number of comments from Wikipedia’s talk page edits which have been labeled by human raters for toxic behavior. The types of toxicity are:
 - toxic
 - severe_toxic
 - obscene
 - threat
 - insult
 - identity_hate
 
The designed model must predict a probability of each type of toxicity for each comment. The dataset is given through the following files:
 - train.csv - the training set, contains comments with their binary labels
 - test.csv - the test set, the model must predict the toxicity probabilities for these comments
 - test_labels.csv - labels for the test data; value of -1 indicates it was not used for scoring

The dataset is under [CC0](https://creativecommons.org/share-your-work/public-domain/cc0/), with the underlying comment text being governed by [Wikipedia's CC-SA-3.0](https://creativecommons.org/licenses/by-sa/3.0/).

## Python notebooks

The project is divided into 3 notebooks:
 - `toxic_comment_classifier` contains the core kernel, featuring data analysis and machine learning algorithms as logistic regression and naive-bayes
 - `lstm-tcc` contains the LSTM kernel
 - `bert-tcc` contains the BERT fine-tuning kernel
