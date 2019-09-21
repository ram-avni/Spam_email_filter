# Spam Email Classification

## The Problem
It’s  a threefold problem:
* It clutters our inbox
* Fraudulent emails 
* Risk of losing the job interview email which got misclassified  in the spam folder

Data Source: <br />
 <br />UCI - Spam Spambase Data Set: https://archive.ics.uci.edu/ml/datasets/Spambase   
Collection of spam e-mails came from postmaster and individuals    
Collection of non-spam e-mails came from filed work and personal e-mails

---
## Target Variable and Features


* A spam, classified as 1, is a Positive (non-spam is 0)

* Number of Instances: 4,601 (1,813 Spam = 39.4%)


* Most of the attributes indicate whether a particular word or character was frequently occuring in the e-mail.  
* The run-length attributes (55-57) measure the length of sequences of consecutive capital letters. 

---

## Base Model:  Naive Bayes

Commonly used for text classification, like spam email, and much more:  
* Language detection
* Author identification
* Sentiment analysis
* Age/gender identification
* Subject identification

Score:  
- Accuracy: 0.80
- Precision: 0.75
- Recall: 0.72
- F1 Train: 0.70
- F1 Test: 0.74
- AUC: 0.78

---

## Base Model:  Naive Bayes - Visuals

<p align="center">
  <img width="460" height="460" src="http://github.com/ram-avni/prj_3_classification/blob/master/visuals/NB%20-%20cm.png/460/460">
</p>

<p align="center">
  <img width="460" height="300" src="http://www.fillmurray.com/460/300">
</p>


![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/NB%20-%20auc.png)


---

## Model Comparison
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/Model%20comparison.png)

---

## How come NB model has the lowest score?
- Data set contains metadata, not the actual content of the emails
- Bags of words - frequencies

- Assume that with NLP, NB model will be better: 
- Black lists
- Combinations
- Position and conditional independence 

---

## Which performance is most desirable?
- Most NOT desirable - missing your interview email!
- FP = missing an important email
- FN = more spam in your inbox
- Minimize FP 
- Trade off:  sacrifice FN (but that’s a small price to pay)

---

## Most important criterion - Precision
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/precision.png)
---

## Chosen Model:  Random Forest
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/Chosen%20model.png)

---

## Random Forest - Visuals
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/RF%20-%20cm.png)
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/RF%20-%20auc.png)

---

## A closer look at TPR / FPR ratio
- AUC is confusing - seems that AdaBoost has a better curve
- A ratio between 2 other ratios - TPR and FPR
- But we really care about FPR, so what does this ratio mean? 
- It means that if TPR goes down, we get more FN
- But we said 
- if it’s an FN we really don’t care - let it send more spam to my inbox
- it’s a small price to pay, but I keep my FP to minimum

---

## Random Forest:  Features Importance
![](https://github.com/ram-avni/prj_3_classification/blob/master/visuals/RF%20-%20features%20importance.png)
---

## How does Google filter spam?
          
 Markup : * Filters rely on word probabilities:
 - Initially calculates the probabilities of ham and spam classes.
 - Next, calculates the probabilities of ham and spam for each word.
- Constantly collecting data - history and feedback
- Text filter and Client  filter
- Introduction of new AI algorithms resulted in aggressive filtering
- Mainly problematic to businesses

- Defeating Bayesian filters
- Text poisoning
- Visuals



