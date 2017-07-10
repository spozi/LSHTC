#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Mon Dec 12 02:38:43 2016

@author: syafiqpozi
Converting words to features
"""

from sklearn.externals.joblib import Memory
from sklearn.datasets import load_svmlight_file

mem = Memory("./mycache")
@mem.cache

filename = ""

def get_data():
    X, y = load_svmlight_file(filename, multilabel=True)
#    print(data)
    return X, y
#    return data[0], data[1]

X, y = get_data()
#Collect all class combination as a set of classes
set_classes = set()
for label in y:
    setLabels = set()
    for y_ in label:
        setLabels.add(y_)
    set_classes.add(frozenset(setLabels))
#    set_classes.add(setLabels)

ctr = 0
dict_set_classes = {}
for l in set_classes:
    dict_set_classes[l] = ctr
    ctr += 1
    
    
print("Total combination of classes: " + str(ctr))
#print("Total number of features: " + str(X[1]))

#2. Create a new list class
list_labels = []
for label in y:
    setLabels = set()
    for y_ in label:
        setLabels.add(y_)
    list_labels.append(dict_set_classes[frozenset(setLabels)])

#for i in list_labels:
#    print(i)    
#        
    
#Convert into csv
#1. Get the total number of dimension
#maxFeatures = 0
#for x in X:
#    print(len(x))
#    if x[1] > maxFeatures:
#        maxFeatures = x[1]
print("Total number of instances: " + str(X.shape[0]))
print("Total number of features: " + str(X.shape[1]))
