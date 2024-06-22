# LEVERAGING CLUSTERING FOR BOOKING PATTERN FORECASTING: A CASE STUDY

## Table of Contents
* [Introduction](#introduction)
* [Navigation in Repository](#navigation-in-repository)
* [File Descriptions](#file-descriptions)
* [Description of the dataset](#description-of-the-dataset)
* [Forecasting models used](#forecasting-models-used)
* [Clustering models used](#clustering-models-used)
* [Packages to include](#packages-to-include)
* [Conclusions](#conclusions)
* [Contact](#contact)

## Introduction 
This thesis project focuses on evaluating various models for forecasting booking patterns, utilizing data from [Sunweb](https://www.sunweb.nl/), a leading holiday package provider in Europe. The core objective is to determine the effectiveness of incorporating clustering into forecasting models. The rationale behind clustering is straightforward: by training models at the cluster level, where more homogeneous booking patterns exist, models can better capture underlying trends. By conducting a comparative analysis, I aim to assess the value added by clustering compared to traditional forecasting models. Therefore, this study will evaluate the performance of ensemble models that integrate information from clustering alongside other forecasting methods and will be compared to a benchmark model. 

**Research Question**: To what extent can clustering techniques improve the accuracy of booking forecasts for holiday packages?

## Navigation in Repository

```
├── code/
│   ├── forecasting_models.ipynb/
│   │   ├── Data preparation
│   │   ├── Model definition 
│   │   ├── Clustering
│   │   ├── Ensemble models
|   |   └── Evaluation 
│   └── clustering.ipynb/
│       ├── Data preparation
│       ├── Clustering
│       └── Understand Clustering
├── visualizations/
│   ├── visualisations.ipynb
│   └── figures(13)    
├── README.md
├── cheatsheet.md
└── final_results_tables.md
```
### File Descriptions
- `forecasting_models.ipynb` : includes all the code for all the forecasting models (1 benchmark model, 4 other forecasting models, 6 ensemble models). This includes hyperparameter tuning, model selection, and evaluation
- `clustering.ipynb`: includes all code for clustering optimization, visualisations and insights generated. (3 clustering models)
- `visualisations.ipynb` : includes all code to reproduce all figures used in this thesis


## Description of the dataset
The dataset used in this analysis consists of cross-sectional data indexed by every holiday package’s departure week. For each departure week, the dataset includes information on the destination airport, destination country, and the number of passengers who booked a holiday package during a specific booking week. Additionally, for the booking weeks present in the dataset, the corresponding revenue and margin generated by Sunweb is captured.

## Forecasting models used
1. [Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html)
   - Trained under two scenarios: model 4.1.2.1 and model 4.1.2.2
2. [Weighted Linear Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html#sklearn.linear_model.LinearRegression)
   -  Trained under two scenarios: model 4.1.3.1 and model 4.1.3.2
3. [Ridge Regression](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html)
    - Hyperparameter tuning for value `alpha`
4. [Regression Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeRegressor.html)
   - Hyperparameter tuning for `max_depth`, `min_samples_leaf` , `min_samples_split' , `max_features`


## Clustering models used
1. [TS k-means Clustering](https://tslearn.readthedocs.io/en/stable/gen_modules/clustering/tslearn.clustering.TimeSeriesKMeans.html)
   - For two different models : Clustering 4.2.1.1 using the average booking patterns and Clustering 4.2.1.2 using the booking patterns aggregated in pairs.
2. [K-means clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) 
   - For Clustering 4.2.2.1 : Using global Features extracted from the booking patterns

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
  <li> Clustering is a useful method in booking pattern forecasting. 
  <li> Clustering the booking patterns is a useful way to group booking patterns, due to its unsupervised nature. 
  <li> The best performing clustering method is using the TS k-means algorithm.
  <li> The ensemble models that utilized clustering outperformed all the other models, including the benchmark model; which was not always outperformed by the general models.
  <li> Regarding the general models; the weighted linear regression and regression trees were the most useful.
</ol>

## Contact
Created by [@annitziak](https://github.com/annitziak) - feel free to contact me!
