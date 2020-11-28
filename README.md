# Pytorch_sentiment_analysis
This repository contains different methods for finding classifying text into sentiments. The source of this data is https://nlp.stanford.edu/sentiment/index.html .
The challenge in classifying this data is the fact that it has **5 sentiment** categories along with not many training examples. There are **8544 training** examples, **1101 validation** examples and **2210 test** data points.
The techniques that has been implemented are as follows:

## LSTM with Attention

**Bidirectional LSTM** models were trained along with **attention** to predict the sentiment of the test data. **GLoVE 300d embedding** has been used for this purpose. This method gave a **test accuracy** of approximately **47%**.

## Convolutional Neural Networks

A **CNN model** was trained with **3 different filter sizes** to predict the sentiment. Although the test accuracy was only slightly lower as compared to the LSTM network, we noted that it is **considerably faster** than that of the LSTM network. The accuracy achieved was approximately **45%**.

## Bidirectional Encoder Representations from Transformers (BERT)

After using LSTM and CNN networks, the **embedding from BERT** was used in a network to predict the sentiment. Due to the lack of too many datapoints, this method was very prone to **overfitting**. However, on using the **last 4 layers of the BER**T representation and passing them through a **Bidirectional GRU**, a significant improvement was seen on the performance on the test data. It achieved an accuracy of **approximately 50%**. Another important thing that seemingly played an important role in this model was the selection of the **batch size**. As it was lowered to 8, the best results were achieved.
