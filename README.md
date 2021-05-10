# Fake News Detection

## Datasets

The dataset which was used in the detector was [Liar](https://www.cs.ucsb.edu/~william/data/liar_dataset.zip)

**LIAR** is a publicly available dataset for fake news detection. A decade-long of 12.8K manually labeled short statements were collected in various contexts from POLITIFACT.COM, which provides detailed analysis report and links to source documents for each case. This dataset can be used for fact-checking research as well. Notably, this new dataset is an order of magnitude larger than previously largest public fake news datasets of similar type. The LIAR dataset4 includes 12.8K human labeled short statements from POLITIFACT.COM’s API, and each statement is evaluated by a POLITIFACT.COM editor for its truthfulness.

You can use the **[download.sh](./download.sh)** file to download the dataset from the site.

## Preprocessing

Six classes where mapped to fake and real outputs
```
True -> Real
Mostly-True -> Real
Half-True -> Real
Mostly-False -> Fake
False -> Fake
Pants-On-Fire -> Fake
```

* Stemming
* Removal of puncutations
* Removal of Stopwords

## Strategy

The strategy which was used was ensemble of classifiers.

## Classifiers

These are the five classifiers which were used in the ensembling, the hyperparameter tuning was done using the library optuna.

* Random Forest
* Logistic Regression
* Multinomial Naive Bayes
* Support Vector Classifiers
* SGD Classifier

## Project Directory Structure

```
|-- Detector.ipynb
|-- LICENSE
|-- README.md
|-- download.sh
|-- metric_data
|   |-- count_test_metric.csv
|   |-- count_train_metric.csv
|   |-- count_valid_metric.csv
|   |-- tfidf_test_metrics.csv
|   |-- tfidf_train_metrics.csv
|   `-- tfidf_valid_metrics.csv
`-- requirements.txt

1 directory, 11 files
```