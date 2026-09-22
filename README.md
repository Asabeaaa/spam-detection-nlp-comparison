# Spam Detection: TF-IDF vs Self-Trained Embedding vs Pretrained GloVe

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#spam-detection-tfidf-vs-self-trained-embedding-vs-pretrained-glove)

## Overview

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#overview)

This project explores spam email detection using natural language processing and deep learning. It compares three text representation approaches:

* **TF-IDF**: Represents text based on the importance and frequency of words within the dataset.
* **Self-Trained Embedding**: Learns word representations directly from the training data.
* **Pretrained GloVe**: Uses pretrained Global Vectors for Word Representation (GloVe) embeddings to represent words based on their semantic relationships.

The models are evaluated using standard classification metrics to compare their performance in distinguishing between spam and legitimate (ham) emails.

## Dataset and Preprocessing

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#dataset-and-preprocessing)

The project uses the **Enron Spam Dataset**, which contains **33,716 email records**. The dataset contains three main fields:

* **Subject**
* **Message**
* **Spam/Ham**

The dataset contains **17,171 spam emails** and **16,545 ham emails**.

Text preprocessing and exploratory analysis were performed before training the models. The project also examines the distribution of spam and ham messages and the words associated with each class.

## Model Comparison

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#model-comparison)

The project compares different approaches to representing email text before classification:

| Approach                   | Description                                                                     |
| -------------------------- | ------------------------------------------------------------------------------- |
| **TF-IDF**                 | Represents words based on their importance within the dataset                   |
| **Self-Trained Embedding** | Learns word representations from the training data                              |
| **Pretrained GloVe**       | Uses pretrained word embeddings to capture semantic relationships between words |

Each approach is evaluated using metrics including **accuracy, precision, recall, and F1-score**, alongside confusion matrices to examine classification performance.

## Results

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#results)

The results section compares the performance of the three approaches using the selected evaluation metrics.

The comparison helps assess how traditional text representations, embeddings learned from the dataset, and pretrained word embeddings perform for spam detection.

## Technologies Used

[svg](https://github.com/Asabeaaa/spam-detection-tfidf-embeddings-glove#technologies-used)

* Python
* TensorFlow / Keras
* Pandas
* NumPy
* Scikit-learn
* NLTK
* Gensim
* Matplotlib
* WordCloud
* KaggleHub
