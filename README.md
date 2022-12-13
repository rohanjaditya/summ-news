# Abstractive News Summarization from scratch using Keras
CS767 Machine Learning Term Project - Spring 2022 (Boston University)

## Dataset Description

The data set was obtained from Kaggle - [News Summarization](https://www.kaggle.com/datasets/sbhatti/news-summarization)
</br>

The data set is a combination of three data sets - XSum, CNN/Daily Mail, and Multi-News. </br>
It contains the Content, Summary, and source data set of the article. There are 870,521 rows and 5 columns, out of which only 2 are used in this project. </br></br>
The Content column contains the news articles to be summarized. It has 870,487 non-null objects.</br>
The Summary column contains the target summaries of the articles. It has 870,521 non-null objects.

## Preprocessing
Several preprocessing steps have to be performed before the data is ready to be
passed to the model for training. This is done to drop unwanted characters,
symbols, and numbers from the data. These serve no purpose to our model and are
therefore removed. </br>
The following preprocessing steps are performed on the content and summary text.
- Drop NULL values
- Drop duplicate rows
- Expand contractions
- Remove HTML tags
- Remove non-alphabet characters
- Remove extra whitespaces
- Remove stopwords
- Remove short words
</br>
Rows for which the lengths of the content or summary are too short or too long arealso removed. Rows for which the length of the content is less than that of the summary are also dropped. </br> 
*START* and *END* tokens are added to the beginning and end of the summary text respectively. </br>
Basic exploratory data analysis is done to determine the maximum lengths to be set for the content and summary texts. 

## Model and Training
Summ-News is am exaample of abstractive text summarization, where new and shorter sentences are created from the original text. These new phrases may or may not be present in the original text. </br>

A sequence-to-sequence model is employed at the heart of Summ-News. There are three LSTM layers in the encoder and 1 LSTM layer in the decoder. An attention layer is also used at the end of the sequence.

## Evaluation
The evaluation metrics used to gauge the performance of the model are the BLEU and ROUGE scores. Two flavors of ROUGE - ROUGE-1 and ROUGE-L are used to measure model performance. </br>

## Results
An average BLEU score of 0.3058 was obtained by Summ-News. </br>
The average ROUGE-1 and ROUGE-L F-1 scores were 12.88 and 11.24, respectively.
