+++
date = "2016-05-06"
title = "Machine Learning (Coursera)"
thumbnail = "images/avatar.jpg"
tags = [
    "machine learning",
    "coursera",
]
categories = []
+++

Recently I've started (again) a course of [Machine Learning on Coursera](https://www.coursera.org/learn/machine-learning/). These are some notes about the course.

Machine Learning problems can be seperated into two major parts: Supervised and Unsupervised machine learning.

Supervised machine learning is when we have some right answers for some amount of inputs and want to predict right anwsers for different inputs.

In Unsupervised machine learning programs we does not have any right anwsers it makes clastering of data.

To understand them better, here are some examples.

## Supervised Machine Learning Example

### Regression Problem

Let's say we want to predict housing prices. And we have some data about the prices of houses and what was the total area of each house.

| Area in m2 (x) | Price in USD (y) |
| :----:  | :-------------: |
|  70     |  80000          |
|  75     |  88000          |
|  80     |  95000          |
|  90     |  101000         |
|  96     |  104000         |
|  100    |  106000         |
|  105    |  107000         |
|  110    |  108000         |
|  115    |  110000         |
|  123    |  112000         |
|  126    |  111000         |
|  132    |  114000         |
|  138    |  116000         |
|  142    |  116500         |

Lets plot the dataset, on the horizontal (x) axis we will have area of the house and the vertical (y) axis will be the price.
<iframe width="100%" height="371" seamless frameborder="0" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQwtGAKD8kGDtF5YPVoLjvIjUe7FjzDMRnJ99bcq1Vxj_3JAOjjQ-Nlxexuvx4FjWFKOH6OHGKUOotQ/pubchart?oid=942513605&amp;format=interactive"></iframe>


Now we need to come up with a function that takes area and tells us the predicted price.

Let's say x - is the area of the house and y is the price from the dataset.

So we need to come up with a differentiable function h(x) that gives us minimum of following (h(x)-y)2 (Squared error function). The function can be linear, quadratic, cubic, logaritmic etc. For example lets say we want to find a linear function that best fits our dataset.
General representation of linear function would be: h(x) = Θ0 + Θ1x. So we need to choose Θ0 and Θ1 that gives us the closest results to y.

#### Summary:

Hypothesis: hΘ(x) = Θ0 + Θ1x
Cost Function: J(Θ0, Θ1) = 1 / 2m Σ(hΘ(xi) - yi)2 where i changes from 1 to m where m is a number of training examples
Goal: minimize J(Θ0, Θ1)

Later we will discuss algorithms that helps us to reach the goal. now let's discribe another example of supervised machine learning

## Classification

In this case we have finite number of 'y's or h(x) can give us only finite number of results. Let's say we want to predict cancer for patients, is it malignant or benign. Similar machine learning problem would be defining a letter is a spam or not.

So our data can be something like this:


|  Size  |  Age  | Malignant or Benign |
|  :---: | :---: | :-----------------: |
|    1   |   10  |      Benign         |
|    2   |   30  |      Benign         |
|    3   |   23  |      Benign         |
|    4   |   33  |      Benign         |
|    5   |   15  |      Benign         |
|    5   |   31  |      Benign         |
|    6   |   45  |      Benign         |
|    6   |   53  |      Malignant      |
|    7   |   35  |      Benign         |
|    7   |   60  |      Benign         |
|    8   |   29  |      Benign         |
|    9   |   48  |      Malignant      |
|    1   |   53  |      Malignant      |
|    1   |   25  |      Malignant      |
|    1   |   30  |      Benign         |
|    1   |   55  |      Malignant      |
|    1   |   62  |      Malignant      |
|    1   |   65  |      Malignant      |
|    1   |   54  |      Malignant      |
|    1   |   54  |      Malignant      |
|    1   |   63  |      Malignant      |


<iframe width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQAxy7ItDT1IylUbk4cnHOS4M3uu7IytRw5Z_ed_M3MUz1jAjnvWPiJCk0dROVsJakaEeH3gZAHHnoG/pubchart?oid=1029865512&amp;format=interactive"></iframe>

In this case the task is to find a function that seperates red and blue dots from each other. the function will seperate whole surface into two parts. The area with the most red dots in it will be benign part and the other part of the surface would be malignant.

In these examples there are used one or two of features to predict something, but in real world examples there will be lots of features that should be considered to before we the prediction. If you understand how this works with one or two features it is not hard apply that knowledge for multiple features. Later I will try to describe how to do this.

## Unsupervised Machine Learning Example

### Clastering

In supervised machine learning we were given a data with some labels, for example we had data of tumor were we knew which row was malignant or benign, in unsupervised machine learning data does not have any labels. So we are given a dataset with no labels and we need to find some structure in the dataset. These kind of problems are called clastering problems.

Good example of the clastering problem would be a google news. What google news does it finds lots of articles on the web, finds similaries / structure in those articles and groups them by the subject.

Other examples of unsupervised learning or clastering can be, Market segmentation or astronomical data analysis etc.

Lets visualize the problem to better understand what we are talking about.

<iframe width="600" height="371" seamless frameborder="0" scrolling="no" src="https://docs.google.com/spreadsheets/d/e/2PACX-1vQAxy7ItDT1IylUbk4cnHOS4M3uu7IytRw5Z_ed_M3MUz1jAjnvWPiJCk0dROVsJakaEeH3gZAHHnoG/pubchart?oid=1626164497&amp;format=interactive"></iframe>

So we have same data as in tumor problem, only without labels. And we need to find the groups of data that can be seperated.


