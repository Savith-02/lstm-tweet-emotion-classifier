# Tweet Emotion Classifier

This project is about classifying the emotion of tweets using a LSTM model. The model is trained on a dataset of tweets, each labeled with one of six emotions: joy, sadness, anger, fear, love, or surprise.

## Project Overview

The project is divided into several steps:

1. **Data Preprocessing**: The tweets are cleaned and tokenized. Stop words are removed and each word is reduced to its base form using lemmatization.

2. **Word Embeddings**: Word embeddings are generated using the Word2Vec model. These embeddings are used to convert the words in the tweets to vectors that can be used as input to the LSTM model.

3. **Model Training**: The LSTM model is trained on the preprocessed tweets. The model's architecture includes an LSTM layer followed by a fully connected layer and a softmax layer.

4. **Model Evaluation**: The model's performance is evaluated on a separate test set. The evaluation metrics used are accuracy, precision, recall, and F1 score.

5. **Loss Visualization**: The training and test losses are plotted against the number of epochs to visualize the model's learning process.

The code for the project is contained in a Jupyter notebook named `tweet-emotion-classifier.ipynb`.

## Running the Project

To run the project, open the Jupyter notebook and run all the cells:

```bash
jupyter notebook tweet-emotion-classifier.ipynb
