# Depretect: depression detection with a LDA model

In the github we collect the materials used for our Final Project of the course Applications for NLP II.

## Introduction 

Depression is one of the most prominent problems in younger generations and one of the most difficult to detect in time. Therefore, in this GitHub we train a model capable of detecting texts with depression as a theme in posts on the social network Reddit using the Latent Dirichlet Allocation (LDA) method.

## Corpora

For this project we have used the English depression related posts from Reddit corpus. This data is available in [Kaggle](https://www.kaggle.com/datasets/luizfmatos/reddit-english-depression-related-submissions?resource=download).
The dataset is in JSON format but, in the code, it is transformed to CSV. 

This CSV has a total of 32165 rows (one post per row) and 24 columns (e.g. user, date, edition, etc.). Of these 24 columns, we kept the three we were interested in for topic modeling ('body', 'subreddit_name' and 'title'). 
Another interesting fact is that the average number of words per text is 235'39.

## Methodology

In this code, we have preprocessed the text with the spacy package "en_core_web_sm" in order to tokenise the text, extract POS tags, etc. Stopwords and other characters have been removed and only open-class words have been kept. 
Finally, in this preprocessing, the 100 most frequent collocations have been extracted and all the preprocessing has been saved in a new column. Subsequently, it has been vectorised and an LDA model has been created which is able to differentiate 100 topics in the texts. 

## Results 

The code results in graphs showing the most frequent words by topic, word similarity and document similarity. Lastly, the performance of this model has a Log Likelihood of -15679211.22011435 and a perplexity of 1491.4019398256091.

## Future Work

We encourage researchers to reuse our code in order to improve its performance. In addition, other datasets from different social networks can also be applied. Finally, it is worth mentioning the great usefulness of this type of models for the early detection of mental disorders through language processing. 

## References
