# udacity-nanods-disaster-response-pipeline
Udacity data science nano degree - disaster response pipeline project

## Summary
This project uses disaster data from Appen (formally Figure 8) to build a model for an API that classifies disaster messages. An ETL pipeline is used to combine data and prepare it for training of a classifier. The classifier is deployed in a web app where messages can be entered to be classified.

## Web app
The web app displays some statistics on the training data and provides an interface for classification of messages. The screenshot is shown below.
 ![Image of web app](/images/web_app.png)

## Detail

**ETL Pipeline**
The file `process_data.py` runs the ELT pipeline. The pipeline:
- Loads messages and categories data
- Cleans the data
- Saves the data to SQLlite database

**ML Pipeline**
The file `train_model.py` runs the ML pipeline. The pipeline:
- Loads data from SQLite database
- Splits the data into training the test sets
- Builds a text processing and machine learning pipeline
- Trains and tunes the model
- Outputs test scores for the model
- Saves model as a pickle file

**Webapp**
- Displays some statistics on data
- Provides interface to classify messages

## Files

| File name                      | Description                                                                                                  |
|--------------------------------|--------------------------------------------------------------------------------------------------------------|
| ETL Pipeline Preparation.ipynb | Jupyter notebook exploring the data and testing out the Extract, Transform and Load process.                 |
| ML Pipeline Preparation.ipynb  | Jupyter notebook exploring the NLP process, selecting classifiers and tuning hyperparameters.                |
| process_data.py                | Implements ETL. Data is saved in the SQLite database messages.db.                                            |
| train_model.py                 | Creates model, tuning hyperparameters, fitting it to training data in messages.db and saves it to model.pkl. |
| run.py                         | Loads model and deploys in Flask web app.                                                                    |
| messages.csv                   | List of messages with IDs.                                                                                   |
| categories.csv                 | Category data for each message ID.                                                                           |

## Requirements
The main dependencies of this project as as follows:
- Flask
- nltk
- numpy
- pandas
- plotly
- scikit-learn
- SQLAlchemy
A full list of requirements is in *requirements.txt*. This project does not use Anaconda.
