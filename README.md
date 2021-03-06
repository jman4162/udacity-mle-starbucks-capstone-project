# udacity-mle-starbucks-capstone-project
The capstone project for Udacity's machine learning engineer (MLE) nanodegree program.

## Project Overview

The object of this capstone project is to answer two business challenges using the Starbucks dataset:
* Can we use data to build a predictive model to determine whether a customer will view and complete a promotional offer based on the offer characteristics and customer demographic information?
* Can we use offer characteristics and customer demographic data to predict how much revenue a completed offer will generate after subtracting reward costs?

I analyze five different machine learning (ML) predictive model solutions and compare their performance for three case studies. These predictive models allow the business to personalize the characteristics of each promotional offer based on each customer’s demographic profile to maximize the probability that the customer views and completes a promotional offer. Additionally, the regression model predicts how much revenue a completed promotional offer generates after subtracting the reward cost to help the business maximize return on investment (ROI) per customer. 

See the [project report](https://github.com/jman4162/udacity-mle-starbucks-capstone-project/blob/main/HodgeJohn_Udacity_MLE_Capstone_Report_v1.pdf) for a detailed write-up and analysis.

## Installation

This project is written in Python 3 using Jupyter notebooks. The relevant Python packages include:
* numpy
* matplotlib
* scikit-learn
* pandas
* pytorch
* seaborn
* json

## File Descriptions

The key files for this project are:
* `01_Starbucks_Capstone_notebook_dataExploration_and_Cleaning.ipynb` : Code notebook used for data exploration, cleaning, and customer segmentation.
* `02_convertTranscriptData.ipynb` : Code notebook used for the preprocessing of the transcript dataset.
* `03_scikit-learn_trainModel_OfferCompleted.ipynb` : Code notebook used for data preproccessing and training machine learning (ML) models using scikit-learn to predict completed offers.
* `04_starbucksUdacity_trainDNN_classifier_offerCompleted.ipynb` : Code notebook used for data preproccessing and training deep learning model using PyTorch to predict completed offers.
* `05_scikit-learn_trainModel_OfferViewed.ipynb` : Code notebook used for data preproccessing and to train ML models using scikit-learn to predict viewed offers.
* `06_starbucksUdacity_trainDNN_classifier_offerViewed.ipynb` : Code notebook used for data preproccessing and training deep learning model using PyTorch to predict viewed offers.
* `07_trainRegression_OfferCompleted.ipynb` : Code notebook used for data preproccessing and training ML models using scikit-learn to predict customer revenue.
* `08_starbucksUdacity_trainDNN_regression_regAdjRev_v2.ipynb` : Code notebook used for training the DNN regression model using PyTorch to predict customer revenue.
* `HodgeJohn_Udacity_MLE_Capstone_Report_v1.pdf` : Final project report.


## Data

The [datasets](https://drive.google.com/drive/folders/12Sq7xssp154Dl5Dqhmc_ZYgkGzDylhbj?usp=sharing) for this project are available here. Processed datasets used in this project are available in this [folder](https://github.com/jman4162/udacity-mle-starbucks-capstone-project/tree/main/trainingData).

The structure of the dataset provided Starbucks Capstone project notebook is structured as follows. Three files contain the data:
* `portfolio.json` - containing offer ids and metadata about each offer (duration, type, etc.)
* `profile.json` - demographic data for each customer
* `transcript.json` - records for transactions, offers received, offers viewed, and offers completed

The three types of offers presented in the `_type` column of `portfolio.json` are:
* Buy-one-get-one (BOGO): a user needs to spend a certain amount to get a reward equal to that threshold amount.
* Discount: a user gains a reward equal to a fraction of the amount spent. 
* Informational offer: there is no reward, but neither is there a required amount that the user is expected to spend.

Here is the schema and explanation of each variable in the files:

`portfolio.json` - Size: 10 offers by six fields
* *id* (string) - offer id
* *offer_type* (string) - type of offer, i.e., BOGO, discount, informational
* *difficulty* (int) - minimum required spend to complete an offer
* *reward* (int) - reward given for completing an offer
* *duration* (int) - time for offer to be open, in days
* *channels* (list of strings)

`profile.json` - Size: 17,000 users by five fields
* *age* (int) - age of the customer
* *became_member_on* (int) - date when customer created an app account
* *gender* (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* *id* (str) - customer-id
* *income* (float) - customer's income

`transcript.json` - Size: 306,534 offers by four fields
* *event* (str) - record description (i.e., transaction, offer received, offer viewed, etc.)
* *person* (str) - customer-id
* *time* (int) - time in hours since the start of the test. The data begins at time t=0
* *value* (dict of strings) - either an offer id or transaction amount depending on the record

## Project Proposal

The accepted [project proposal](https://github.com/jman4162/udacity-mle-starbucks-capstone-project/blob/main/HodgeJohn_Udacity_MLE_Capstone_Proposal_v2.pdf) document is available here.

## Conclusions

Overall, this project was surprisingly challenging due to the structure of the `transcript.json` dataset and the preprocessing required to generate useful ML model predictions. However, I learned a lot in this project and developed solutions to the challenges discussed in the project proposal:
* Developed predictive ML models to classify whether views and completes a promotional offer based on personalized customer and offer characteristics
* Developed predictive ML models to determine how much a customer spends by completing an offer after subtracting out the reward cost. The ML predictive model outperforms the benchmark model in each of our three studies, and the benchmark models also perform pretty well.
* Determined the features that are most significant to whether or not a customer views and completes a promotional offer
* Defined key customer segment groups based on customer demographics

The models and insights developed in this project allow the company to understand the primary drivers of an effective and profitable promotional offer. The predictive models will enable the company to personalize the characteristics of each promotion to maximize its odds of success for each customer. This project is an excellent example of how machine learning models benefit marketing campaigns and create business value. Lastly, this project shows why a more efficient and straightforward machine learning model is often preferable to a larger and more complex deep learning model.

