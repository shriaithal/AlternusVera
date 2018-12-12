# Alternus Vera 

Course code : **CMPE-257** 
    
Group name : **Codebusters**
    

### Liar Liar Pants on Fire Dataset Description 
- It has 3 files test, training and valid.
- Each file has 14 columns
   - Column 1: the ID of the statement ([ID].json).
   - Column 2: the label.
   - Column 3: the statement.
   - Column 4: the subject(s).
   - Column 5: the speaker.
   - Column 6: the speaker's job title.
   - Column 7: the state info.
   - Column 8: the party affiliation.
   - Column 9-13: the total credit history count, including the current
    statement. 9: barely true counts, 10: false counts, 11: half true counts, 12: mostly true counts, 13: pants on fire counts.
   - Column 14: the context (venue / location of the speech or statement).
        
## Business Problem

Fake news problem is too important to ignore especially after recent election of Donald Trump. These news are like malignant tumor that causes moral treats. It is nothing but a nassault on truth. Being impartial about the real news are same as that of a deliberate lies.

The main purpose of this project is to identify essential features that can be trusted to predict if a news is fake or not. These features are realted to the news content. Our key classification is to predict if a news is fake or not based on these features. In addition, we are also intended to learn various deep learning and neural networking techniques and compare their performances.


We initially as a team performend literature survey on list of features that has so far played major role in popularising a fake news. Each member of the team took one major feature and performed distillation process. We vectorized and came up with embedding vectors. Computed polynomial equation and classified the news articles based on all the below features. 


### Process Steps: 
- Load the Data
- Distillation Process
    - Data Cleaning and Text Preprocessing
    - Visualization
    - Sentiment Analysis  
    - LDA Topic Modelling
    - word2Vec Word Embedding 
    - TF-IDF Vectorization
    - Doc2Vec using individual feature
- Vector Classification Modeling 
- Ranking and Importance
- Compute Polynomial Equation **[(0.6 *Clickbait) + (0.1 *Sensationalism) + (0.2 *Political Affiliation Feature) + (0.1 *Context)]**
- Perform Classification Prediction 


### Feature Selection
**Top Features Selected based on research articles**

1. Political Affliation
2. Sensationalism
3. Clickbait 
4. Context Modeling   
5. Spam  

*Other simple features as a part of distillation:*

6. Sentiment Analysis 
7. LDA Topic Modeling  
8. Ranking

### Contributions:


|Features |  Member |
|-----|-----|
| Political Affiliation              |  Anushri| 
| Sensationalism/Psychology Utility |  Harini |  
| Clickbait                         |  Ravi   | 
| Context/Venue                     |  Sunder | 
| Spam                              |  All | 

As a team, we decided on the importance of the factors presented above. We brainstormed on the general pre-processing techniques we did want to use. We also had common visualization methods and similar techniques for evaluating the classification model accuracy. Each of us enriched the dataset with individual features and persisted it in a csv file. Each feature vector is persisted on csv (which is distilled with LDA, sentiment scores). We also came up with a polynomial equation based on the factors and the accuracy scores we received by classification. The polynomial equation is then used to build a model for fake news classification. The **polynomial equation that we have used is (0.6*Clickbait) + (0.1 *Sensationalism) + (0.2*Political Affiliation Feature) + (0.1*Context)**. The final model that we built is a variation of the stack ensemble technique. Stacked generalization is an ensemble method where the models are combined using another machine learning algorithm. The basic idea is to train machine learning algorithms with training dataset and then generate a new dataset with these models. Then this new dataset is used as input for the combined machine learning algorithm. The combined model is then used to predict the fakeness in the corpus. We as a team were able to achieve an accuracy of 57% using the various supervised learning techniques specified in this paper.
