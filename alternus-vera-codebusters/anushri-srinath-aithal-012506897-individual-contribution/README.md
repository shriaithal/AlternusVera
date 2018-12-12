### Political Affiliation

- Name: Anushri Srinath Aithal
- Student ID: 012506897
- Team: Codebusters
- Feature: Political Affiliation

#### Business Problem

The widespread propagation of false information online is not a recent phenomenon but its perceived impact in the 2016 U.S. presidential election has thrust the issue into the spotlight. Technology companies are already exploring machine learning-based approaches for solving the problem. In this project, we are using NLP based text classification to identify the different news categories.

#### Data

- Politifact Liar Liar Data - https://drive.google.com/open?id=1IVl4Qt92LZwvMlnJGRcEZVKF-dpawhdz
- **Note:** The Google Data set used for spell checker is 1.5GB. Cannot be checked in to GitHub. Please download data from the link to the input_data folder - https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit

**Description of the Data:**
- Column 1: the ID of the statement.
- Column 2: the label.
- Column 3: the statement.
- Column 4: the subject(s).
- Column 5: the speaker.
- Column 6: the speaker's job title.
- Column 7: the state info.
- Column 8: the party affiliation.
- Column 9-13: the total credit history count, including the current statement.
- Column 14: the context (venue / location of the speech or statement).

#### Features for Fake News Classification from Fake News Article

1. Social acceptance = # of likes, # of comments (short term utility)
2. Bias Score
3. Spam Score
4. Website credibility/ Domain Ranking
5. Author credibility
6. Political Affliation
7. Occurance Location (Probability of announcing on Radio or Press release being fake is low)
8. Sensationalism/Psychology Utility - agreeing with reader's prior beliefs
9. Frequency Heuristic - Constant repetition makes them believe (Sensationlism)
10. Echo Chamber - Forming groups and spreading opinions
11. Visual - Images, Links, Videos

#### Political Affiliation

Political bias/affliation towards certain political parties, political leaders can influence fake news origin. An unbiased view on media reports requires an understanding of the political bias of media content. According to the paper "Automating Political Bias Prediction" by "Felix Biessmann", political power appears to be strongly correlated with positive sentiment of a text. 

#### What did not work?

As a part of Sprint 1 of Alternus Vera, I started out trying to analyze the attitude towards a political dictionary. The political dictionary from the Stanford Political Library (https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VHXN5F) provides a set of words with a polarity indicating the attitude with which people percieve those words. I applied various NLP methodologies in this approach namely - COunt Vector, TF-IDF, Word2Vec and Doc2Vec approach using the dictionary of words and its polarity for vectorization. These approaches however did not provide satisfactory accuracy for classification of Fake News. I was able to achieve only **19%** accuracy. This approach clearly did not work for me and all the steps followed in this approach is part of another notebook namely **political_affiliation_implA.ipynb**

#### What worked?

As mentioned above, using political affiliation alone as a feature did not yield a great result. Also, the word overlap between the Standford dictionary and Liar Liar dataset was poor. In this notebook a novel approach of distillation is used to improve the classification accuracy. Without distillation, an accuracy of **37%** was achieved. Post distillation accuracy is **54%**. The entire process performed is laid out in the next section and the steps are explained briefly in this notebook.

#### Feature Engineering: Political Affiliation Vector Approach 5 Steps

1. Data Preprocessing
2. Data Visualization: Word Length Distributions, Fake News Label Distribution, Word Cloud Visualization, t-SNE visualization, Political Affiliation Label Visualization
2. Custom dictionary based on word frequency
3. TF-IDF and Classification on Political Affiliaition Labels
4. Doc2Vec and Classification on Political Affiliation Labels
5. Distillation by performing Sentiment Analysis
6. Distillation by performing LDA. Visualization of topic distribution.
6. Distillation by performing Ranking based on Speaker importance. Visualization of top 10 Speakers distribution.
7. Classification of Fake News based on the Political Affiliation vector.

#### Data Preprocessing

1. Encode the labels to 0 and 1 where 1 represents data that are original, true, mostly-true and 0 represents fake and falsified news
2. Convert all textual data from upper case to lower case.
3. Remove stop words
4. Perform spell check
5. Wordnet Lemmatization for verbs
6. Stemming using snowball filter
7. Remove punctuation from all textual fields.
8. Remove short words, words containing less than 3 letters.