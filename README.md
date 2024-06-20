# LEVERAGING CLUSTERING FOR BOOKING PATTERN FORECASTING: A CASE STUDY

## Table of Contents
* [Introduction](#introduction)
* [Description of the dataset](#description-of-the-dataset)
* [Forecasting models used](#forecasting-models-used)
* [Clustering models used](#clustering-models-used)
* [Packages to include](#packages-to-include)
* [Conclusions](#conclusions)
* [Contact](#contact)

## Introduction 
This thesis project focuses on evaluating various models for forecasting booking patterns, utilizing data from [Sunweb](https://www.sunweb.nl/), a leading holiday package provider in Europe. The core objective is to determine the effectiveness of incorporating clustering into forecasting models. The rationale behind clustering is straightforward: by training models at the cluster level, where more homogeneous booking patterns exist, models can better capture underlying trends. By conducting a comparative analysis, I aim to assess the value added by clustering compared to traditional forecasting approaches. Therefore, this study will systematically evaluate the performance of various forecasting techniques. Specifically, ensemble models that integrate information from clustering alongside other forecasting methods will be analyzed.

**Research Question**: To what extent can clustering techniques improve the accuracy of booking forecasts for holiday packages?

## Description of the dataset
The dataset used in this analysis consists of cross-sectional data indexed by every holiday package’s departure week. For each departure week, the dataset includes information on the destination airport, destination country, and the number of passengers who booked a holiday package during a specific booking week. Additionally, for the booking weeks present in the dataset, the corresponding revenue and margin generated by Sunweb is captured.

## Forecasting models used
1. [Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
2. [Weighted Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html#sklearn.linear_model.LinearRegression)
3. [Ridge Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html)
4. [Regression Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)

## Clustering models used
1. [TS k-means Clustering](https://tslearn.readthedocs.io/en/stable/gen_modules/clustering/tslearn.clustering.TimeSeriesKMeans.html)
2. [K-means clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) using Features extracted from the booking patterns

## Packages to include
List of required Python packages:
- pandas
- seaborn
- matplotlib
- numpy
- scikit-learn
- tqdm
- tslearn
- scipy
- statsmodels
- fastdtw

To install these packages, look at `requirements.txt` file with these dependencies and use `pip install -r requirements.txt` to install them.

## Conclusions
<ol>
  <li>Clustering is a useful method in booking pattern forecasting. 
  <li>Clustering the booking patterns is a useful way to group booking patterns, due to its unsupervised nature. 
  <li> The best performing clustering method is using the TS k-means algorithm.
  <li>The ensemble models that utilized clustering outperformed all the other models, including the benchmark model; which was not always outperformed by the general models.
<li> Regarding the general models; the weighted linear regression and regression trees were the most useful.
</ol>

## Contact
Created by [@annitziak](https://github.com/annitziak) - feel free to contact me!
