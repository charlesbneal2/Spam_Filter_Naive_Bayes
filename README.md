# Spam Filter: Project Overview
- Implemented a Naive Bayes algorithm to classify SMS messages as "Spam" or "Not-Spam" (aka "Ham") with 98% accuracy

## Code and Resources Used
**Python Version:** 3.7

**Packages:** pandas, re

**Dataset:** https://archive.ics.uci.edu/ml/datasets/SMS%2BSpam%2BCollection

## Data Overview and Test Split
The dataset consists of 5,574 SMS messages that have been manually labeled as either "spam" or "ham" (a legitimate message). Overall, 13.41% of the dataset consisted of spam messages. I chose an 80:20 train:test split and confirmed that each set had roughly 13% spam content. 

![image](https://user-images.githubusercontent.com/97380323/177211197-ae9aae90-3e3b-4b1c-9684-839d2ac2cd97.png)


## Data Cleaning
I "dummy-coded" the "SMS" and split it into a number of distinct columns, each representing one word in the training set vocabulary. For each row, each column contains an integer representing the number of instances of a specific word in that message. This required reformatting the "SMS" column to remove all punctuation and casing. 

![image](https://user-images.githubusercontent.com/97380323/177211130-cea7e613-82e6-4eff-8240-f55dcc588e4e.png)

## Computing Constants and Parameters
I computed several constants necessary for the Naive Bayes Algorithm: the probability that a message is spam, the probability that a message is ham, the number of words in all spam messages, the number of words in all ham messages, and the number of unique words in the vocabulary. For each unique word in the overall vocabulary, I computed the probability that probability of encountering each word given that a message is spam and the probability of encountering the word given that a message is ham. 

## Building the Classification Function
The classifier takes an SMS string and uses the Naive Bayes algorithm to compute the probability that it is Spam and the probability that it is Ham given its contents. It returns a label 'spam' or 'ham' based on which label is more likely.

## Testing the Classifier
Against the 20% holdout test set, the classifier achieved 98% accuracy. This would be very useful for an app which automatically sorts message inboxes.
