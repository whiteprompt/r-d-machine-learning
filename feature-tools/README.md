# Feature Engineering with Featuretools

## Introduction
Feature Engineering (FE) is the process to create new features from existing data available to train machine learning models. Since a machine learning model will learn from the data that is provided, this process becomes one of the most crucial steps in creating a model. Building relevant features can be the difference between having a model that performs well or not.

Commonly, FE is a manual step, relying on domain knowledge, data manipulation and also intuition. It is a boring step and the final features will be limited both by time and human creativity. In recent years, we have observed an increase in the number of tools created to automate the creation of a project, including frameworks developed for automated feature engineering. Today we are going to see how to use one of these tools.

Featuretools is an open source python library designed to automatically create features from a set of related tables. This library is based on this paper: [Deep Feature Synthesis: Towards Automating Data Science Endeavors](https://groups.csail.mit.edu/EVO-DesignOpt/groupWebSite/uploads/Site/DSAA_DSM_2015.pdf). Deep Feature Synthesis (DFS) uses pre-defined mathematical functions, which are called `feature primitives`, to aggregate and transform data across many tables.

## Problem to Solve
We want to illustrate how easy is to create new features using featuretools without having any domain knowledge of an specific business. Using this framework, we can spend effort in other tasks or create more complex features.

We will use a dataset with information about individuals applying for loans with [Home Credit Group](https://www.homecredit.net/) (HCG), a lender specialized in loans individuals with little credit history. HCG hopes to be able to predict if an applicant is to default on their loan, in order to choose whether a given loan plan is good for an applicant. Below there's a diagram showing each table, its information and how each table is related to each other table.
![Home Credit Default Risk](./docs/home_credit.png)

## Journey
We could manually go through all these tables and create a lot of features based on them, but this would give not just a lot of manual work, but a lot of decisions related to design. Featuretools allows us to define our datasets and the relationships between them, and automatically extracts features from child datasets into parent datasets using DFS. We will use it to create features from the data in the secondary tables in the HCG dataset, and keep features which are informative.

Here you can find the code regarding to manual feature engineering and FE using featuretools:
1. [Manual Feature Engineering](notebooks/manual_fe.ipynb)
2. [Automated Feature Engineering with Featuretools](notebooks/featuretools_fe.ipynb)