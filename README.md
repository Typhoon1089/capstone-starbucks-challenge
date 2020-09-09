# Starbucks Capstone Challenge - Data processing and analysis

## Introduction<a name="introduction"></a>
This challenge is a part of the Udacity capstone, we will work with Starbucks' datasets. We process and analyze the one-month data to get insights which helps Starbucks in making decisions on its future campaign. The detailed findings can be found in the conclusion of my notebook.

The main purpose of this project is to understand the business flow. So far, existing solutions can be found on the Internet. However, the authors simply evaluated the number of _offer_received_, _offer_viewed_ and _offer_completed_ in the `customer transaction` history while ignoring their orders and the time instant those events happened. As a result, the provided numbers are incorrect though the findings are still considered. The detailed assumptions and workflows con be found in the first part (Part #0) of my notebook.

After data analysis, two possible tasks which can be started include (i) Customer segmentation and (ii) Customer prediction (i.e., to predict whether customers respond to offers or not). However, I decided to NOT cover them here because:
* This task has smaller datasets compared to the Arvato project (i.e. another project of mine)
* Starbucks has many products, so amount of data for only one product is not enough to classify customers

## Dataset<a name="data"></a>
The Starbucks' data is contained in three files:

* portfolio.json - containing offer ids and meta data about each offer (duration, type, etc.)
* profile.json - demographic data for each customer
* transcript.json - records for transactions, offers received, offers viewed, and offers completed

Here is the schema and explanation of each variable in the files:

**portfolio.json**
* id (string) - offer id
* offer_type (string) - type of offer ie BOGO, discount, informational
* difficulty (int) - minimum required spend to complete an offer
* reward (int) - reward given for completing an offer
* duration (int) - time for offer to be open, in days
* channels (list of strings)

**profile.json**
* age (int) - age of the customer 
* became_member_on (int) - date when customer created an app account
* gender (str) - gender of the customer (note some entries contain 'O' for other rather than M or F)
* id (str) - customer id
* income (float) - customer's income

**transcript.json**
* event (str) - record description (ie transaction, offer received, offer viewed, etc.)
* person (str) - customer id
* time (int) - time in hours since start of test. The data begins at time t=0
* value - (dict of strings) - either an offer id or transaction amount depending on the record


## Project organization<a name="organization"></a>
1. `data/:` folder that contains the datasets (i.e., the mentioned 3 files)
2  `images:` folder that contains images for my notebook
3. `cache/:` folder that contains parameters during model development.
4. `Starbucks_Capstone_notebook.ipynb:` the main notebook that presents all steps of the project.

## Installation<a name="installation"></a>
The project is conducted using Amazon SageMaker and then tested in my local machine which (Python 3.6)

