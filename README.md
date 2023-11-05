# Breast Cancer Malignant-Benign Classification


## Context

October is the breast cancer awareness month. 
Breast cancer is a major public health issue. It was responsible for 685000 deaths around the globe in 2020 (WHO: https://www.who.int/fr/news-room/fact-sheets/detail/breast-cancer). Half of the breast cancer cases in women appear without any risk factor other than sex and age. About 0.5-1% of breast cancers appear in men.
It is thus interesting to find new ways to detect breast cancer, especially at early stages when the disease can be treated with efficacity. We can consider tumor characteristics obtained through X-ray.

![image](https://github.com/FoMelanie/breast_cancer_classification/assets/87911606/3606d5e2-3474-4745-aed8-0ee2dbd1769f | width=100)


Starting from the Breast Cancer Dataset on Kaggle (https://www.kaggle.com/datasets/yasserh/breast-cancer-dataset), the goal is to classify samples as:
- *Malignant*: the tumor is cancerous, which means that it grows quickly, often invade surrounding tissues and can spread to other parts of the body (metastasis)
- *Benign*: the tumor is not cancerous, which means that it grows slowly with distinct borders, it does not invade surrounding tissues and does not spread to other parts of the body

## Data

The dataset can be downloaded here and is available in the data folder. Two datasets are present: the original one and a cleaned one after data cleaning (see notebook for the data preparation steps).

## How to run the tumor diagnosis application

You must first install pipenv with ```pip install pipenv``` if not already done.
Then, install the dependencies present in the ```Pipfile``` with the command ```pipenv install``` run in the folder.

If you are on Windows, you can run the application in production environment with this command:

```pipenv run gunicorn --bind 0.0.0.0:9696 application:app```

If you are not working on Windows, you can run the application in production environment with this command:

```pipenv run waitress-serve --listen=0.0.0.0:9696 application:app```

You can test the application prediction with the test python script ```application_test.py``` with this command:

```pipenv run python application_test.py```

The output should be a DiagnosisValue equal to 0 and TumorClassification equal to "Benign".

*Note*: You can also run the application locally with debug mode on with this command line:

```pipenv run python application.py```