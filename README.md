# Zestimate
## Introduction
This repository contains the source codes for [Zillow’s Home Value Prediction (Zestimate)](https://www.kaggle.com/c/zillow-prize-1), a Kaggle competition. 
The goal is to minimize the Maximum Absolute Error between the predicted log error and the actual log error. Log error is defined as
<p align="center">
<img src="https://render.githubusercontent.com/render/math?math=logerror=log(Zestimate)-log(SalePrice)">
</p>

## EDA
- A [Tableau dashboard](https://public.tableau.com/profile/qi.feng1229#!/vizhome/Zestimate_15894928320550/Dashboard3?publish=yes) was created for interactive visualization.
<img src="https://github.com/lullaby1024/zestimate/blob/master/zestimate_tableau_preview.png" width="80%">

## Feature Engineering
- The raw data have 59 features. Towards feature engineering, the following features were dropped and the remaining 22 features were fed into the models.
  - Irrelevant features, e.g., `parcelid` and `transactiondate`
  - Features with too many missing values, i.e., features with > 80% of missing values
  - Constant features: `assessmentyear`
  - Categorical features with too many categories: `propertyzoningdesc`
  - Redundant/Highly-correlated features
    - `regionidneighborhood`, `regionidzip`, `bathroomcnt`, `fullbathcnt`, `calculatedfinishedsquarefeet`, `garagetotalsqft`, `rawcensustractandblock`, `landtaxvaluedollarcnt`, `taxvaluedollarcnt`
