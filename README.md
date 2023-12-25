# Kaggle-Text-to-Emotion-Dataset
Part of the course - Natural Language Processing &amp; Text Mining

Project 1 Bis. Kaggle Text to Emotion Dataset 1
Consider the dataset in https://www.kaggle.com/datasets/pashupatigupta/emotion-detection-from-text/data?select=tweet_emotions.csv where 40K records Twitter dataset are classified into 13 categories: neutral, worry, happiness, sadness, love, surprise, fun sentiment, relief, hate, empty, enthusiasm, boredom, anger.
1.	Initial exploration: You may inspire from some existing programs in Kaggle handling the same dataset, write a script that outputs the histogram of the different categories. Comment on the distribution of the training samples across various categories.
2.	Write a script that concatenates all tweets of the same category and put them on a single file (data frame). Then outputs the top 10 most frequent keywords in each category, before and after processing stage (stopword removal, unusual character removal, e.g., symbols, numbers, repetition.
3.	Write a script that outputs the histogram, of the 10 most frequent tokens in each category (data frame), and draws WordCloud of each data frame.
4.	We want to reduce the number of categories to three categories only, e.g., by focusing on Positive, Neutral and Negative Emotions. For this purpose, suggest a manual crafting of your choice according to your understanding of the meaning of the 13 categories that assigns each category to Positive, Negative or Neutral. Call this construction (A). Present a table the mapping between the 13 categories and three constructed categories.
5.	Suggested an alternative construction of the three categories using word2vec embedding.  For this purpose, use clustering algorithm k-means with k=3 and whose inputs are the 13 word2vec embedding vectors of each of the 13 category titles. Summarize in a table the content of each class (among the three classes) in terms of the 13 categories. Call this construction (B).
6.	Now we want to test each of the construction A and B when considering all data frame of each category. For this purpose, we want to consider a set of rational metrics as criteria for comparing A and B. First, consider the amount of overlap (number of common tokens, after pre-processing and lemmatization). Write a script that computes the total number of common tokens in each class (A common token is a token that occurs in at least two data frames that assigned to the same class). Provide a summary table that synthesizes the number of common tokens for each class in A and in B.
7.	Repeat the preceding when considering the most frequent wording in each data frame. Specifically, by considering the sets of 20 most frequent words for each data frame. Then this metric evaluates the number of common frequent words in data frames of categories belonging to the same class. Summarize the result in a table for A and B.  
8.	We want to find out whether some categories are more prone to mistakes than others. For this purpose, write a script that checks whether a given term has an entry in wordnet lexical database or not. Then output the number of unmatched token in each data frame, and the corresponding percentage (ratio of number of unmatched words over total number of tokens in each data frame). Summarize the result in a concise table.
9.	We want to evaluate the occurrence of some stylometric features, and how this is related to the labelling provided in the dataset. For this purpose, consider the NRC Word-Emotion Association lexicon, downloadable from https://saifmohammad.com/WebPages/NRC-Emotion-Lexicon.htm. For each record k (Twitter of Kaggle dataset), labelled as category j, we calculate the entity: 
    where m is the number of tokens in NRC lexicon that are labelled as category l in record k.     
Write a script that records for each record k and category l (that exists in both NRC and Twitter dataset), the corresponding value of  .
Consider a vector whose dimension is equal to the total number of records. We therefore consider two vectors V1 (labeling vector) and V2 (NRC-based vector). Write a script that constructs for each category k, vectors V1 and V2 so that V1(m) =1 if the record m is labelled to be part of category k, and zero, otherwise; while V2(m) =   (number of tokens of NRC lexicon in category k that occur in record m).   Finally, for each category, use Person correlation function from scipy, stats library or others to calculate Pearson correlation coefficient between V1 and V2. Present the result in a table indicating the Person correlation value and its corresponding p-value for each category. Comment on the mapping between NRC lexicon and labelling of Twitter dataset.  
10.	We want to match the similarity between the title categories with the similarity of the records contained in the corresponding categories. For this purpose, write a function with inputs two categories, say, k1 and k2, and output the similarity between records in k1 and that of k2. For this purpose, use word2vec embedding to calculate the embedding of each records as the average of embedding of words constituting that records. Next, the embedding of the overall list of records in a category is calculated as the mean of the embedding vectors of its records. Finally, the cosine similarity between the two embedding generated from each category is used to estimate the newly created record-based category similarity. To test whether title category similarity matches the record-based category similarity, write a matrix of the record-based similarity between each pair of categories. We claim that there is a matching between the title similarity and record-based similarity if the highest similarity score in both cases occurs for the same category-category pair. Discuss this matching outcome.
11.	Repeat 10) when Glove, FastText, BERT (base) is employed instead of word2vec embedding.
12.	From your previous investigation, feel free to do your own search and suggest an extra state-of-the-art approach for matching category content to category title. Identify appropriate literature to comment on the findings.

