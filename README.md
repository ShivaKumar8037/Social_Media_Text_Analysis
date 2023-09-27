## Social Media Text Analysis: Pre-processing, Tokenization, and Sentiment Exploration

### Overview
In this project, we delved deep into the nuances of text data processing, especially in the realm of social media content. We experimented with various pre-processing techniques, tokenization, and polarity measurement, and explored their implications on further text analysis.

### 1. Dataset
The dataset used is a csv file named 'trainingdata-all-annotations.csv' which contains 2,814 tweets about various targets and the stance of that tweet, opinion, and sentiment of the tweet. Targets included in the dataset are 'Atheism', 'Climate Change is a Real Concern', 'Feminist Movement', 'Hillary Clinton', and 'Legalization of Abortion'. The possible stances are 'Against', 'Favor', and 'None'. The possible sentiments are 'Positive' and 'Negative', and the opinion could be 'Other' or 'Target'.

### 2. Pre-processing of Data

We took the dataset comprising social media content and processed it in two distinct ways:

#### 2.1 Minimal Pre-processing:
   - Anonymized examples by replacing all `@tags` with the word "@tag".
   - Normalized all text from sentence case to lower case but retained fully capitalized words.
   
#### 2.2 Maximal Pre-processing:
   - Removed all `@tags`.
   - Removed all `#tags`.
   - Normalized text to entirely lowercase letters.
   - Developed a “stop word” dictionary/lexicon and filtered out all stop words from the content.

### 3. Tokenization

Post pre-processing, the data from both sets were tokenized using the `CountVectorizer()` for unigram representation. 

#### 3.1 Data Descriptives:
   - Calculated the average length of each instance.
   - Determined the total number of words in the corpus.
   - Measured the average length of content for each target.
   - Assessed the average length of content for each stance type and across different targets.

### 4. Feature Selection: POS Tagging and Polarity Measurement

#### 4.1 POS Tagging:
   - Used the NLTK's `nltk.pos_tag()` method to assign part-of-speech tags to both datasets.
   
#### 4.2 Polarity Measurement:
   - Created two sentiment/polarity lexicons: one for positive sentiment/polarity and another for negative sentiment/polarity.
   - Used these lexicons to compute a score representing the proportion of positive and negative polarity words in each post.
   
#### 4.3 Descriptive Statistics:
   - Derived the average polarity scores.
   - Broke down the average polarity scores by different stances and targets.

### 5. Further Analysis and Discussions

- **NLTK POS Tagging**: We observed that NLTK, which wasn't originally built for social media data, faced challenges while POS tagging such content. The informal nature and mixed languages in social media data often led to inaccurate tags.
- **Polarity in Social Media**: Our descriptive statistics revealed certain patterns in polarity scores across various stances and targets, offering insights into public sentiment on different topics.
- **TF-IDF vs CountVectorizer**: We discussed the scenarios where TF-IDF might be more useful than simple term frequencies, especially in datasets with diverse document lengths or when certain terms are too frequent and might overshadow other informative terms.

### 6. Conclusion
Considering the scope of this project, we learned that polarity score is a valuable metric to measure sentiment. Although the calculation of this score is bound by the words in our lexicon, the implementation offers insights into sentiment patterns in the dataset. This project serves as an essential foundation for further advanced analyses on social media content.
