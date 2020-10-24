# team_cohesion_sentiment_analysis

## Motivation
One of the main determininants for team cohesion is sentiment (emotions). Emotions have a high impact in productivity,
creativity and job satisfaction in teams. GitHub is a popular repository platform where communication is tracked in the 
highly collaborative activity of programming. Performing sentiment analysis on GitHub commit comments can provide insights 
towards team cohesion that can be leveraged to correct dynamics within teams, enforce code of conduct or identify isssues
as they are developing.

## Data
Dataset of GitHub commit comments was obtained from GHTorrent archive. Resulting in a dataset of 6357623 GitHub commits comments.
- http://ghtorrent.org/gcloud.html
- file date: mysql-2019-06-01

## Sentiment Analysis
The NLTK library VADER was used to analyse commit comments for sentiment classification (positive, negative) of dataset.

## Topic Modeling
To find hidden sematic structures (topics) in the text dataset, an unsupervised approached was used.
Latent Dirichlet Allocation (LDA) was the probabilistic model built to perform topic modeling. 

The parameter (number of topics to study with the LDA model) was selected based on the Gensim 
Hierarchical Dirichlet Process (HDP) class which aims to find the number of topics in the data.

## Convert topics to feature vectors
Get the distribution of the 20 topics over each comment. These vectors are considered feature vectors for a supervised statistical model.

## Train supervised classifier
An SVM model was trained with topic feature vectors and VADER predicted sentiment labels.

## Hidden topic relevance
Assessed hidden topics relevance to unseen GitHub commit comments in relation to sentiment analysis.
