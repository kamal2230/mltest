---
title: "Method to find best classifier"
author: "Charles"
date: 2020-08-08
description: "-"
type: technical_note
draft: false
---

```python
from sklearn.naive_bayes import MultinomialNB
from sklearn.naive_bayes import GaussianNB
from sklearn.naive_bayes import BernoulliNB
from sklearn.svm import SVC
from sklearn.neural_network import MLPClassifier
from sklearn.ensemble import AdaBoostClassifier
from sklearn.tree import DecisionTreeClassifier
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import GradientBoostingClassifier
from sklearn.linear_model import LogisticRegression
from sklearn.model_selection import GridSearchCV
from sklearn.metrics import f1_score, confusion_matrix
```


```python
classifiers = {
    'mnb': MultinomialNB(),
    'gnb': GaussianNB(),
    'svm1': SVC(kernel='linear'),
    'svm2': SVC(kernel='rbf'),
    'svm3': SVC(kernel='sigmoid'),
    #FOR SVM USE HYPERPARAMETER TUNING TO BETTER UNDERSTAND WHAT TO TAKE
    'mlp1': MLPClassifier(),
    'mlp2': MLPClassifier(hidden_layer_sizes=[100,100]),
    'ada': AdaBoostClassifier(),
    'dtc': DecisionTreeClassifer(),
    'rfc': RandomForestClassifer(),
    'gbc': GradientBoostingClassifer(),
    'lr': LogisticRegression()
}
```


```python
f1_scores = dict()

for classifier in classifiers:
    
    clf = classifiers[classifier]
    clf.fit(train_x,test_x)
    y_pred = clf.predict(train_y)
    f1_scores[classifier] = f1_score(y_pred, test_y)
    print(classifier, f1_scores[classifier])
```


```python

```
