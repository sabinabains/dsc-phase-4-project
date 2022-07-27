# Overview:

![cyberbullying_pic](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/cyberbullying_pic.png)

Kind Inc. would like help protecting users from hate speech.

# Business Understanding

Over the past couple of months, Twitter has been in the headlines for the potential acquistion of their company from Elon Musk. This has upset many people, as Musk plans to reduce the level of moderation Twitter currently has on potentially harmful tweets. 

This change will likely lead to a massive increase in hate speech and misinformation, and will negatively affect users. Kind Inc. would like our help to create the model behind a browser extension that can flag tweets that are considered cyberbullying. This way, users have the ability to hide tweets from their feed.

# Data Understanding and Processing

We will take a supervised learning approach by using 47,000 tweets that have been manually flagged by cyberbullying type. This is a balanced dataset from Kaggle: [data](https://www.kaggle.com/code/anayad/classifying-cyberbullying-tweets/data). 

The labels are as follows:
  * Age
  * Ethnicity
  * Gender
  * Religion
  * Other type of cyberbullying
  * Not cyberbullying

Each tweet has a maximum of 140 characters. Because this problem requires Natural Language Processing, One-Hot-Encoding must be performed to rearrange the dataset, where each column is a word, and each row has a binary output of 1 if the word is present in the tweet, and 0 if it is not. 

Prior to One Hot Encoding, words are all standardized into lowercase only, and are stemmed. This unifies words that are in different tenses and therefore spelled differently, but have the same meaning. For example implementing our Stemmer to a dataset with the following words: ['CONNECT','CONNECTIONS','CONNECTED','CONNECTING','CONNECTION'] would return them all as the same word; CONNECT. 

Stopwords (words such as "a", "is", "as", "the", etc.) have also been removed, as these words will have a high count even though they do not provide context to the sentence. 

Once data cleaning is completed, our top tokens (or words) per label are as follows:

Top Tokens by Gender:
![gender_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/gender_freqdist.png)

Top Tokens by Age:
![age_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/age_freqdist.png)

Top Tokens by Ethnicity: 
![ethnicity_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/ethnicity_freqdist.png)

Top Tokens by Religion:
![religion_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/religion_freqdist.png)

Top Tokens by Other Cyberbullying:
![other_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/other_freqdist.png)

Top Tokens by No Cyberbullying:
![none_freqdist](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/none_freqdist.png)

An initial look tells us there are some heavy differences in common words used in different types of cyberbullying, however there is some overlap in words in the "other" and "none" cyberbullying categories.

# Modeling

### Multinomial Naive Bayes

Three iterations of Multinomial Naive Bayes were run. Initially, the model was run after only tokenizing the data. This generated the following accuracies. 

* Training Data Accuracy Score: xx.x%
* Testing Data Accuracy Score: xx.x%

The second model was run with a cutoff of 


### Recurrent Neural Networks

# Evaluation

In the end, the recurrent neural network with dropout included generated the highest accuracy score *without overfitting*. This is evident by the small range between the training and testing scores: 

* Training Data Accuracy Score: xx.x%
* Testing Data Accuracy Score: xx.x%

XXXXXXX


![confusion_matrix](https://github.com/sabinabains/dsc-phase-4-project/blob/main/images/confusion_matrix.png)


# Conclusion and Next Steps

   Overall, this result is relatively strong.

# Repository Structure

```
├── data : data used for modeling
├── images : images used in PPT and readme
├── README.md : project information and repository structure
├── dsc-phase-4-project-presentation.pptx : (Presentation for Stakeholders)
└── dsc-phase-4-project.ipynb (jupyter notebook used for modeling)
```
