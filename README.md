# Depretect: depression detection with a LDA model

In this github we collect the materials used for our Final Project of the course Applications for NLP II.

## Introduction 

Depression is one of the most prominent problems in younger generations and one of the most difficult to detect in time. Therefore, in this GitHub we train a model capable of detecting emerging topics from Reddit posts with depression as main theme using the Latent Dirichlet Allocation (LDA) method.

## Corpora

For this project we have used the English depression related posts from Reddit corpus. This data is available in [Kaggle](https://www.kaggle.com/datasets/luizfmatos/reddit-english-depression-related-submissions?resource=download).
The dataset is in JSON format but, in the code, it is transformed to CSV. 

This CSV has a total of 32165 rows (one post per row) and 24 columns (e.g. user, date, edition, etc.). Of these 24 columns, we kept the three we were interested in for topic modeling ('body', 'subreddit_name' and 'title'). 
Another interesting fact is that the average number of words per text is 235'39.

## Methodology

In this code, we has created a code for topic modeling. For doing this, we have preprocessed the texts with the spacy package "en_core_web_sm" in order to tokenise them, extract POS tags, etc. Stopwords and other characters have been removed and only open-class words have been kept. 
Finally, in this preprocessing part, the 100 most frequent collocations have been extracted to join each collocation with an underscore and all the preprocessing has been saved in a new column ("preproc"). With this, we can see that the average number of words per text has changed to 75'30. Subsequently, it has been vectorised and an LDA model has been created, which is able to differentiate 50 topics in the texts. 

## Results 

The model shows different formats of the results. On the one hand, it shows a table with the 50 topics and their respective words with the most weight. For example, topic 0 contains words such as "friend", "people", "talk", "care"...; that is, the topic is related to social relations. Topic 1 has words like "help", "therapist", "talk", "problem"... which could be grouped as clinical help. Topic 2 contains words such as "love", "pain", "mind", "heart"... which are words related to the topic of love break-up. 

On the other hand, we find the results in a bi-dimensional space that groups the 50 themes by similarity. Their distribution could be differentiated as follows: 
- Upper-left side: with descriptive words of the topic of bad situations ("fuck", "tired", "fucking", "hate", "shit"...).
- Upper-right side: social relations topic ("friend", "girl", "mom", "love", "dad"...)
- Lower-left side: sentiments topic ("depression", "help", "hate", "sad"...)
- Lower-right side: routine topic ("job", "school", "work", "class"...)

Other types of results show words and texts by similarity taking a specific word/text as reference. Lastly, the performance of this model has a Log Likelihood of -15679211.22011435 and a Perplexity of 1491.4019398256091.

## Conclusions and Future Work

This model is able to differentiate different topics that are actually problems leading to depression. It can be usefull to detect this kind of sub-problems in texts. Finally, we encourage researchers to improve this model inproving the preprocessing part making it more selective so it deletes words such as "thing" or "see" in order to obtain more specific topics. 
