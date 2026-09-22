# Spam Detection: TF-IDF, Self-Trained Embeddings, and Pretrained GloVe

## Overview

This project explores spam email detection using natural language processing and deep learning. It compares three text representation and modelling approaches using the Enron-Spam dataset:

* **TF-IDF + Feedforward Neural Network**: Uses TF-IDF bag-of-words representations as input to a feedforward neural network.
* **Self-Trained Embedding**: Learns word embeddings directly from the Enron-Spam training data.
* **Pretrained GloVe Embedding**: Uses pretrained GloVe word embeddings with the embedding layer frozen during training.

The same preprocessing pipeline, train/validation/test split, and evaluation metrics were used across the three models to focus the comparison on the effect of text representation.

## Dataset and Preprocessing

The project uses the Enron-Spam dataset, containing 33,716 emails, with 17,171 spam emails and 16,545 ham emails.

The subject and message body were combined into a single text field. The text was lowercased, email addresses and URLs were removed, punctuation and English stopwords were removed, and empty records were dropped.

The data was divided into training, validation, and test sets using a 70/15/15 stratified split:

* 23,601 training emails
* 5,057 validation emails
* 5,058 test emails

A vocabulary size of 8,000 tokens was used. The embedding-based models used sequences with a maximum length based on the 95th percentile of token counts, resulting in a sequence length of 1,374 tokens.

## Model Comparison

The three models used the same overall evaluation protocol.

| Model                  | Accuracy | Precision |  Recall | F1-score |
| ---------------------- | -------: | --------: | ------: | -------: |
| TF-IDF + FFN           |   99.96% |    99.92% | 100.00% |   99.96% |
| Self-Trained Embedding |   99.94% |    99.88% | 100.00% |   99.94% |
| Pretrained GloVe       |   99.64% |    99.31% | 100.00% |   99.65% |

## Results

The **TF-IDF + Feedforward Neural Network** achieved the highest test F1-score at **99.96%**, misclassifying only 2 of the 5,058 test emails.

The **self-trained embedding model** performed almost identically, achieving a **99.94% F1-score** with 3 misclassified emails.

The **frozen pretrained GloVe model** achieved a **99.65% F1-score**, misclassifying 18 ham emails as spam.

A supplementary experiment fine-tuned the pretrained GloVe embeddings instead of keeping them frozen. This increased the F1-score from **99.65% to 99.94%**, matching the self-trained embedding model.

## External Evaluation

The best-performing required model, TF-IDF + FFN, was also evaluated on the **UCI SMS Spam Collection** containing 5,572 messages.

Although the model achieved **86.59% raw accuracy**, it predicted every message as ham, resulting in **0% spam precision and 0% spam recall**. This demonstrates that the high performance on the Enron-Spam dataset did not transfer to the different SMS domain.


## Key Takeaway

The results show that, on the Enron-Spam dataset, TF-IDF and self-trained embeddings performed almost identically, while frozen pretrained GloVe performed slightly lower. Fine-tuning the GloVe embeddings substantially reduced this gap.

More importantly, the external SMS evaluation showed that very high in-domain performance does not necessarily indicate good performance on a different text domain.
