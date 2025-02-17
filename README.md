# Project: Text Analysis of Political Content in Tweets 
**Author:** Amber Ni | **Date:** 02-06-2025 | **Course:** Text As Data: Computational Linguistics

## Project Description
This project analyzes **tweets from polititians**, focused on pre-processing and analyzing textual contents. The project employs various **natural language processing** techniques - follows a systematic workflow, **including**:
1. Document sampling
2. Text preprocessing (tokenization, cleaning, and stemming)
3. Exploratory analysis using word clouds and TF-IDF to visualize word frequencies and highlight discriminative terms
4. Sentiment classification through VADER dictionary to categorize tweets as positive, neutral, or negative
5. Similarity analysis through cosine similarity to measure thematic consistency

The repository **includes**: 
1. Raw tweets data `.csv`
2. R Markdown `.rmd`
3. Output `.html`

The expected outcomes include uncovering **common themes and discriminative terms** in political language, detecting **sentiment patterns** across different politicians and events, and analyzing **linguistic differences** between political parties. Through these analyses, this project aims to provide deeper insights into how politicians craft their messages and engage with the public on social media.

## How to Use This Repository

If you'd like to **run the analysis** on your own laptop, follow these steps:
  1. Download the dataset `tweets_congress.csv` from https://drive.google.com/file/d/14jMDNp-SF4jBigVsZSrmprp2d2Zq__bL/view?usp=sharing. 
  2. Open RMarkdown `Tweets Analysis_Amber.Rmd`.
  3. Change working directory according to your local path - `setwd("~/path/to/your/local/directory")`.
  4. Access the dataset according to where you put you data in - `tweets <- read_csv("~/path/to/your/data")`.
  5. Run all to execute the entire analysis.

## Data Source 

This dataset `tweets_congress` contains **tweets from U.S. politicians**, along with **metadata** such as their name, state, party affiliation, and congressional chamber. Each entry includes the tweet's text, posting date, and, if applicable, the original author in case of a retweet. 

The dataset contains **1,266,542 observations** and **10 variables**.

## Key Analysis and Findings

I **subseted** the dataset by **party affiliation** - only selected tweets from **Democrats**, and only selected **50000 observations** to increase computing efficiency. 

#### Preprocessing Text
The dataset contains raw, unstructured text with emojis, hashtags, mentions, and URLs. **Pre-processing steps after tokenization** included removing stop words, stemming, and filtering out non-relevant characters.

#### Exploratory Analysis of Political Rhetoric
I further **subseted** my dataset by **regions "West" and "Northeastern"** and conducted analysis along this dimension. A comparative review of the **top features** of democratic politicians’ tweets highlighted frequent topics such as LGBTQIA+ rights, immigration policy, and COVID-19. Sentiment-laden words like "useless" and "congrats" revealed emotional undertones in political discourse. 

#### Regional Word Frequency Analysis
I created **2 word clouds** to compare tweets from Western and Northeastern states, showing no significant differences in key topics, with common themes centered around "American," "work," "family," and "community." Using **TF-IDF analysis**, I identified top words that are most distinctive for each group.

<img width="371" alt="Screenshot 2025-02-16 at 11 00 23 PM" src="https://github.com/user-attachments/assets/671605a4-519f-4035-a279-c405c37766f1" />
<img width="355" alt="Screenshot 2025-02-16 at 11 00 34 PM" src="https://github.com/user-attachments/assets/ad9e12f7-5e73-4dc7-96f1-3fac1b956a83" />

#### Sentiment Analysis Using VADER
I used **sentiment labeling using the VADER dictionary** categorized tweets into positive, neutral, and negative sentiment classes. I also created **a bar chart to visualize** the prevalence of my classes, showing positive tweets are the most common type.

<img width="724" alt="Screenshot 2025-02-16 at 10 58 02 PM" src="https://github.com/user-attachments/assets/418f9adf-7bdd-410c-967d-abdd96c3e28f" />

#### Text Similarity Using Cosine Distance and Euclidean Distance
I extracted tweets with the most positive and most negative sentiment scores, as identified by the VADER sentiment analysis model, and used them as reference points. Then, I computed the **cosine similarity** between each tweet and the reference tweets. The top 10 tweets with the highest similarity scores were retrieved. I also computed **Euclidean distance** between the reference tweets and all other tweets in the dataset. The top 10 tweets with the smallest Euclidean distance were retrieved.

#### KWIC Analysis and Dictionary Refinement
I conducted a **keyword-in-context (KWIC) analysis** to inspect key words related to the most frequent features computed by TF-IDF and check if sentiment classification makes sense to these texts. The results shows that sentiment classification may be misleading, as certain words (e.g., "serve", "wage") were more thematic than emotional. This suggests a potential shift towards topic-based classification rather than pure sentiment analysis.


