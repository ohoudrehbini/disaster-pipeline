# disaster-pipeline
## Data Engineering 

## Table of Contents
1. [Project Introduction and motivation](#Project-Introduction-and-motivation)
2. [Instullation](#Instullation)
3. [File Description](#File-Description)
4. [Analysis and Results](#Analysis and Results)
5. [Licensing, Authors, and Acknowledgment](#Licensing-Authors-Acknowledgment)
6. [Instructions](#Instruction)

### Project Introduction and motivation <a name="Project Intorduction and motivation"></a>
Figure Fight are providing pre-labeld tweets and text messages from real life disaster.Disaster Response Messages provides thousands of messages that have been sorted into 36 categories. These messages are sorted into specific categories such as Water, Hospitals, Aid-Related, that are specifically aimed at helping emergency personnel in their aid efforts. the task is to repair the data with ETL pipeline and use Machine learning to build up a supervised learning model. Then filter and then pull out the messages important. 

Thus, The main goal of this project is to build an app (Screenshots below) that can help emergency workers analyze incoming messages and sort them into specific categories to speed up aid and contribute to more efficient distribution of people and other resources.

### Instullation <a name="instullation"></a>
#### ETL pipeline preparation : 
   - import pandas as pd
   - import numpy as np 
   - from sqlalchemy import create_engine
   - import sqlite3
#### ML pipeline disaster 
   - import pandas as pd
   - import numpy as np
   - from sqlalchemy import create_engine
   - from nltk.tokenize import word_tokenize , RegexpTokenizer
   - from nltk.stem import WordNetLemmatizer
   - from sklearn.ensemble import RandomForestClassifier, AdaBoostClassifier
   - from sklearn.multioutput import MultiOutputClassifier
   - from sklearn.feature_extraction.text import CountVectorizer, TfidfTransformer
   - from sklearn.pipeline import Pipeline
   - from sklearn.model_selection import train_test_split
   - from sklearn.metrics import classification_report
   - from sklearn.model_selection import GridSearchCV
   - from sklearn.decomposition import TruncatedSVD
   - import pickle
   - import sqlite3
   - import nltk
   - import re 
   - import string
   - from sklearn.metrics import precision_recall_fscore_support
   - %matplotlib inline
   - import matplotlib.pyplot as plt

##### download:
  - nltk.download('punkt')
  - nltk.download('wordent')
  - nltk.download('stopwords')

### File Description <a name="File Description"></a>
##### Data 
     - categories.csv: dataset including all the categories
     - messages.csv: dataset including all the messages
     - InsertDatabaseName.db : ETL pipeline scripts to read, clean, and save data into a database
     - DisasterResponse.db: output of the ETL pipeline, i.e. SQLite database containing messages and categories data
##### app
     - run.py: Flask file to run the web application
     - templates contains html file for the web application

##### Model 
     - train_classifier.py: machine learning pipeline scripts to train and export a classifier
     - classifier.pkl: output of the machine learning pipeline, i.e. a trained classifier
     
     
### Analysis and Results <a name="Analysis and Results"></a>
##### Analysis 
###### Data Preparation
- Modify the Category csv; split each category into a separate column
- Merge Data from the two csv files (messages.csv & categories.csv)
- remove duplicates and any non-categorized valued
- create SQL database DisasterResponse.db for the merged data sets
###### Text Preprocessing
- Tokenize text
- remove special characters
- lemmatize text
###### Build Machine Learning Pipeline
- Build Pipeline with countervectorizer and tfidtransformer
- Seal pipeline with multioutput classifier with random forest
- Train Pipeline (with Train/Test Split)
- Print classification reports and accuracy scores
###### Improve Model
- Preform GirdSearchCV
- Find best parameters
###### Export Model as .pkl File
- use pickle.dump 

##### Results 
1. Created an ETL pipeline to read data from two csv files, clean data, and save data into a SQLite database.
2. Created a ML pipeline to train a multi-output classifier on the various categories in the dataset.
3. Created an app to show data visualization and classify any message that users would enter on the web page.

### Licensing, Authors, and Acknowledgment <a name="Licensing, Authors, and Acknowledgment"></a>
Thanks to Udacity for the starter code and FigureEight for providing the data set to be used by this project.

### Instructions <a name="instructions"></a>
1. Run the following commands in the project's root directory to set up your database and model.
    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`
2. Run the following command in the app's directory to run your web app.
    `python run.py`
3. Go to http://0.0.0.0:3001/
