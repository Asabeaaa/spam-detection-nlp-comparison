# Spam Detection: TF-IDF vs Self-Trained Embedding vs Pretrained GloVe

## Overview

This project explores spam email detection using natural language processing and deep learning. It compares three text representation approaches:

* **TF-IDF**: Represents text based on the importance and frequency of words within the dataset.
* **Self-Trained Embedding**: Learns word representations directly from the training data.
* **Pretrained GloVe**: Uses pretrained Global Vectors for Word Representation (GloVe) embeddings to represent words based on their semantic relationships.

The models are evaluated using standard classification metrics, including accuracy, precision, recall, and F1-score, to compare their performance in distinguishing between spam and legitimate (ham) emails.

## Dataset and Preprocessing

The project uses the Enron Spam Dataset, which contains 33,716 email records, with 17,171 spam emails and 16,545 ham emails. It contains three main fields:

* **Subject**
* **Message**
* **Spam/Ham**



