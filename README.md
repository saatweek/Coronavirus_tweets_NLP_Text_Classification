# Coronavirus Tweets NLP Text Classification

## [About the Dataset](https://www.kaggle.com/smid80/coronavirus-covid19-tweets)
> ***CONTEXT*** <br>
> This dataset contains the Tweets of users who have applied the following hashtags: #coronavirus, #coronavirusoutbreak, #coronavirusPandemic, #covid19, #covid_19<br><br>From about 17 March, the dataset also included the following additional hashtags: #epitwitter, #ihavecorona<br><br>This is the first dataset in the series, as the Data tab only displays 20 files at a time and I have been uploading files with a single day's worth of data. To ensure that all files are visible to users and no files are too large, it seems prudent to create a second dataset to split the files into manageable groups of approximately half a month. The first file also contains a file that matches country with country_code and may be useful for users.<br><br>
> ***CONTENT***<p>The dataset contains variables associated with Twitter: the text of various tweets and the accounts that tweeted them, the hashtags used and the locations of the accounts.</p>Note that due to the large volume of Tweets, there may be some gaps for some hashtags (not all Tweets with a given hashtag may be captured). Because some hashtags are used less frequently than other hashtags, less frequently used hashtags may span a longer period of time (going back earlier) than more frequently used hashtags. The hashtag "#coronavirus" seems to be the most frequently used - despite scraping 500,000 Tweets, there was no overlap between Tweets with this hashtag in version 1 and version 5, therefore gaps remain.<br><br>The retweets argument has been set to FALSE, so this dataset does not include retweets (although a count of retweets is provided as a variable).
<br>

## Approaches Used 

- ***[Embedding](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(Embedding).ipynb)***<br>Embedding is probably the most basic approach to classify text
>[Word embedding](https://en.wikipedia.org/wiki/Word_embedding) is the collective name for a set of language modeling and feature learning techniques in natural language processing (NLP) where words or phrases from the vocabulary are mapped to vectors of real numbers. Conceptually it involves a mathematical embedding from a space with many dimensions per word to a continuous vector space with a much lower dimension.

- ***[Bi-Directional LSTM](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(LSTM).ipynb)***

- ***[1-D Convolution](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(1D_Convolutions).ipynb)***

- ***[BERT](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/Corona_Tweets_Classification_(BERT).ipynb)*** *(using ktrain)*

![Accuracy Comparison](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/newplot.png)

![Accuracy on Validation Data](https://github.com/saatweek/Coronavirus_tweets_NLP_Text_Classification/blob/master/comparison%20on%20validation%20data.png)
