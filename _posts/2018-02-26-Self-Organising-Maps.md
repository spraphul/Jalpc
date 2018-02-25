---
layout: post
title:  "Self Oraganising Maps"
date:   2018-02-26
desc: 
keywords: ""
categories: [Tutorial]
tags: [Machine Learning,Unsupervised]
icon: 
---

In this Tutorial, we will discuss about a machine learning algorithm called Self
Organising Maps. Before we go into the details of the model, I would like to 
clear the meanings of some of the terms that we will be using further frequently.

## Supervised Learning
Let us suppose we are given a dataset in which the the input data along with the 
corresponding labels are already given. In such problems, we usually build a model 
which takes a new feature vector and outputs the most appropriate label for it and
this type of learning is called Supervised Learning.

## Unsupervised Learning
In this case we are only aware of the input feature vectors and we have no idea about 
the label corresponding to the input. In such cases, a specific set of algorithms are 
used which basically oraginises or maps the dataset in some k-dimensional plane in the 
form of clusters where each cluster represents an unique label. These types of learning
algorithms are said to be Unsupervised.

## SOM Introduction
SOM also known as Kohenen's Self Organising Maps is an unsupervised learning algorithm which maps the dataset onto a plane and the plane can be any dimensional. Intuitively, it can be considered as a clustering algorithm. Now, if the dimension of the plane over the data is to be mapped is less than that of input data, we can say that SOM also contributes in reducing the dimension of data(data compression). But the best part of SOM is that despite of reducing the dimensions, it does not result in losing topological relationships of the data. 

## Architecture
![Alt text](../Image10.jpg?raw=true "Title")

SOM is a lattice of neurons distributed on a plane over which the data is to be mapped. Each neuron has its centre and weight 
vector. The dimesion of the weight vector is same as that of input data and the dimension of centre depends on the dimension of the plane over which we need to map the data.
The figure given above is an example of a 2-D SOM where the neurons are distributed on a 2-Dimensional plane and thus their centre co-ordinates will also be 2-dimensional. Let us assume the input data has a dimension Nx1. Then each neuron 
will have a weight vector of dimension Nx1.

![Alt text](../Figure1.jpg?raw=true "Title")

The second figure is an image showing exactly how a two dimensional SOM works. The left part of the figure is the original data distributed randomly over the plane. The right part is the output of SOM which has done a clustering of the entire dataset.








