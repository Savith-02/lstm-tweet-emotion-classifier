# Tweet Emotion Classifier

This project is about classifying the emotion of tweets using a LSTM model. The model is trained on a dataset of tweets, each labeled with one of six emotions: happiness, love, neutral, sadness, surprise, or worry.

## Project Overview

The project is divided into several steps:

1. **Data Preprocessing**: The tweets are cleaned and tokenized. Stop tweets are removed and some reduced into more simpler terms.

2. **Word Embeddings**: Word embeddings are generated using the GloVe (Global Vectors for Word Representation) model. These embeddings are used to convert the words in the tweets to vectors that can be used as input to the LSTM model. The GloVe model used is `glove.twitter.27B.50d`, which was trained on Twitter data and can be downloaded from the [Stanford NLP Group's website](https://nlp.stanford.edu/projects/glove/).

3. **Model Training**: The LSTM model is trained on the preprocessed tweets. The model's architecture includes an LSTM layer followed by a fully connected layer and a softmax layer. The performance of the model is evaluated with varying dropout rates and both unidirectional and bidirectional LSTM layers.

4. **Model Evaluation**: The model's performance is evaluated on a separate test set. The evaluation metrics used is accuracy.

5. **Loss Visualization**: The training and test losses are plotted against the number of epochs to visualize the model's learning process. The variations of train and test losses with varying dropout rates and unidirectional/bidirectional natures are shown in the diagram below:

    ![Diagram](Diagram-1.png)

- The code for the project is contained in `tweet-emotion-classifier.ipynb`.
- The code used for preprocesing the raw csv is in `data-cleaner.ipynb`.

## Dataset

The dataset used for this project is the "Emotion Detection from Text" dataset, which can be downloaded from [Kaggle](https://www.kaggle.com/datasets/pashupatigupta/emotion-detection-from-text). 
A subset of the original dataset was used for training the model, specifically focusing on the six largest classes. However, the distribution of these classes in the derived dataset is not uniform, leading to a skewed dataset. The class distribution in the derived dataset is as follows:

- happiness: 3617
- love: 2694
- neutral: 6299
- sadness: 3806
- surprise: 1510
- worry: 6272
- 
## Note on Loss Calculation

The training and evaluation functions have been updated to average loss over the total number of examples, not the number of batches. This change ensures consistent loss values across different batch sizes. As a result, the magnitude of loss values in new plots may differ from previous ones, but the general trend remains consistent.

## Limitations

The performance of the model may be affected by the nature of the tweets. Tweets are often very vague, lack context, and contain spelling errors. These factors can make it difficult for the model to accurately classify the emotions.

In particular, the word embeddings used in this model may not be able to capture the meaning of misspelled words or words used in unconventional ways, which are common in tweets. This is a known limitation of word embeddings.

Future work could explore techniques for handling these issues, such as using character-level embeddings, incorporating a spell-checking step in the preprocessing, or using models specifically designed for understanding the informal language used in social media.
