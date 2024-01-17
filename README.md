# LangAI-Assignment
## About the project
In the context of author classification in Eastern and Western Europe, this article investigates the comparative efficacy of augmenting complexity in binary classification models. The core findings underscore the importance of advanced model architecture in author attribution. The broader significance lies in refining frameworks enhance information retrieval systems, contributing to a nuanced understanding of online discourse.

## File Explaination
 **Note**: Before running any of the notebooks make sure to download the data provided by the course and place the file nationality.csv in a folder named 'Data' in the same directory as the notebooks. It is recommended you run the files in the *provided order*.

### 1) Preprocessing.ipynb 
Here we take the original data and standerdize it before training as well as add new columns to it, mainly with linguistic features.\
<ins> Standardization include </ins> : lowercasing, removing stop words, lemmatization, tokenization and removing non-english tokens\
<ins> Feature exploration include </ins> : average word length, average sentence length, TTR, NER, punctuation count, number of unique words, number of characters, number of contractions and text subjectivity.

The final dataset after preprocessing is stored as a csv file called 'tokenized_eng.csv' in the 'Data' folder.

There is also some topic modeling and exploration, however due to time constraints we were unable to fully explore it as a dimension.

### 2) Undersampling_dataset.ipynb
Here, we load the preprocessed dataset from the 'Data' folder and do under-sampling. The final under-sampled data is stored as a csv file in the 'Data' folder. 

### 3) Word2Vec_embeddings.ipynb
Here, the Word2Vec model is trained with pre-trained GloVe vectors (Twitter data) and then the model is used to create word embeddings and 
subsequently document embeddings for our input data. Each dimension (total of 100) is converted to a separate feature of each document and thus
the feature matrix with all features to test (including features created during the preprocessing step such average sentence length, etc) are stored in a dataframe
and saved as a csv file in the 'Data' folder. 

**Note:** The pr-trained GloVe vectors were obtained from the following source: https://nlp.stanford.edu/projects/glove/. Under the sub-heading 'Download pre-traiened word vectors',
download the Twitter vectors via the zip file named: 'glove.twitter.27B.zip'. Within the file, copy the 'glove.twitter.27B.100d.txt' file into the 
'Data' folder.

### Model Exploration

### 4) Logistic_Regression.ipynb
Here, we have the option of exploring two different models: 1) baseline simple logistic regression (**without** document embeddings as features) or 2) simple logistic regression (**with** document embeddings as features) 
When prompted to chose between the two models, make sure to enter a valid input (explained in detail in the file) else the prompt will be repeated until a valid input is made.
All the model's evaluation metrics including F1 score, precision and recall across classes are displayed along with accuracy and MCC (Mathew's Correlation Coefficient). The 5-fold CV results are also displayed

### 5) Neural_network.ipynb
Here, we have the option of exploring the neural network built using the document embeddings as features. All the model's evaluation metrics including F1 score, precision and recall across classes are displayed 
along with accuracy and MCC (Mathew's Correlation Coefficient). The most optimal hyperparameters were discovered through hyperparameter tuning by analyzing several test and train loss graphs. The train and test loss graphs of the final model with chosen hyperparameters 
is also displayed. 

### 6) FastText.ipynb
Here, we can explore the FasText model trained to carry out the binary classification task. All the model's evaluation metrics including F1 score, precision and recall across classes are displayed 
along with accuracy (both training and testing) and MCC (Mathew's Correlation Coefficient). The 5-fold CV results are also displayed.

### 7) NB model.ipynb
Here, we...
