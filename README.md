# Coronavirus Tweets NLP Text Classification

## Contents
- [Libraries Used](#libraries-used)
- [About the Dataset](#about-the-dataset)
- [Approaches Used](#approaches-used)
- [Accuracy Comparison](#accuracy-comparison)

## Libraries Used
- Pandas
- Tensorflow 2.x
- Numpy
- Plotly

## [About the Dataset](https://www.kaggle.com/smid80/coronavirus-covid19-tweets)
> ***CONTEXT*** <br>
> This dataset contains the Tweets of users who have applied the following hashtags: #coronavirus, #coronavirusoutbreak, #coronavirusPandemic, #covid19, #covid_19<br><br>From about 17 March, the dataset also included the following additional hashtags: #epitwitter, #ihavecorona<br><br>This is the first dataset in the series, as the Data tab only displays 20 files at a time and I have been uploading files with a single day's worth of data. To ensure that all files are visible to users and no files are too large, it seems prudent to create a second dataset to split the files into manageable groups of approximately half a month. The first file also contains a file that matches country with country_code and may be useful for users.<br><br>
> ***CONTENT***<p>The dataset contains variables associated with Twitter: the text of various tweets and the accounts that tweeted them, the hashtags used and the locations of the accounts.</p>Note that due to the large volume of Tweets, there may be some gaps for some hashtags (not all Tweets with a given hashtag may be captured). Because some hashtags are used less frequently than other hashtags, less frequently used hashtags may span a longer period of time (going back earlier) than more frequently used hashtags. The hashtag "#coronavirus" seems to be the most frequently used - despite scraping 500,000 Tweets, there was no overlap between Tweets with this hashtag in version 1 and version 5, therefore gaps remain.<br><br>The retweets argument has been set to FALSE, so this dataset does not include retweets (although a count of retweets is provided as a variable).
<br>

## Approaches Used 

- ***[Embedding](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(Embedding).ipynb)***<br>Embedding is probably the most basic approach to classify text. [Wikipedia](https://en.wikipedia.org/wiki/Word_embedding) defines it as
>[Word embedding](https://en.wikipedia.org/wiki/Word_embedding) is the collective name for a set of language modeling and feature learning techniques in natural language processing (NLP) where words or phrases from the vocabulary are mapped to vectors of real numbers. Conceptually it involves a mathematical embedding from a space with many dimensions per word to a continuous vector space with a much lower dimension.

I think of it as assigning various properties to a word. The actual properties assigned are definitely unknown, but just for the sake of explanation, we'll define 3 categories, i.e., cute, funny, toxic. And then, with each word, we'll assign a vector with 3 values which tell us how cute, funny and toxic that word is. So for example, mask can be [0.5, 0.3, 0.002] and Covid might be [0.001, 0.02, 0.98] and Distancing could be [0.3, 0.45, 0.0001].<br>What it does is, that the similar words then have similar values, and the distinct words with opposite meaning will have wildly different values.<br> If the sentence majorly consists of funny/cute words then the sentence would be classified as good, otherwise bad<br>Link to the code with the explanation of each line is [here](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(Embedding).ipynb)

- ***[1-D Convolution](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(1D_Convolutions).ipynb)*** <br>1-D Convolution works further on the embedding matrix and passes a filter over the embedding matrix of the entire sentence, essentially extracting some essential featres from the bigger embedding matrix and condensing into a smaller matrix which is faster to train and often, more accurate.<br>Detailed code [here](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(1D_Convolutions).ipynb)

- ***[Bi-Directional LSTM](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(LSTM).ipynb)*** <br>Bi-Directional LSTMs are basically really advanced RNN's where the "memory" of both the previous words, and the upcoming words are reatined and passed onto the Recurrent Neural Network. This provides additional context (as compared to normal RNN) and results in a more accurate classification than that of a regular RNN, bidirectional RNN, GRU's, embeddings and 1-D Convolutions<br>Link to the code is [here](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(LSTM).ipynb)

- ***[DistilBERT](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(BERT).ipynb)*** *(using ktrain)* <br> BERT stands for **B**idirectional **E**ncoder **R**epresentations from **T**ransformers.<br>[DistilBERT](https://huggingface.co/transformers/model_doc/distilbert.html) is a small, fast, cheap and light Transformer model trained by distilling BERT base. It has 40% less parameters than bert-base-uncased, runs 60% faster while preserving over 95% of BERT’s performances as measured on the GLUE language understanding benchmark.<br>This is being run by [ktrain](https://github.com/amaiya/ktrain), which is a lightweight wrapper used to help build, train, and deploy neural networks and other machine learning models (DistilBERT in this case) <br>Link to the code is [here](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(BERT).ipynb)

## Accuracy Comparison

![Accuracy Comparison](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/newplot.png)

![Accuracy on Validation Data](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/comparison%20on%20validation%20data.png)
