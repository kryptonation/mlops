# ML Workflow refresher + Train first model

**Goal:** Learn the end-to-end ML pipeline for experimentation (data preparation -> model training -> evaluation) and integrate into MLOps repo.

## ML Workflow overview

- **Data Ingestion** Load database (csv, database, API)
- **Data cleaning & Preprocessing** Handle missing values, scaling, encoding
- **Feature engineering** Create meaningful features from raw data
- **Model training** Train a model using libraries like scikit-learn
- **Model evaluation** Check accuracy, precision, recall, etc.
- **Model persistence** Save the trained model as a .pkl or .joblib

## **Hands-on** Titanic survival prediction

We will build a binary classification model (Survived/Not survived) using the famous Titanic dataset.

## Folder structure update

```
mlops-course
+-- src
|   +-- data
|   |   +-- titanic.csv
|   +-- models/
|   +-- pipelines/
|   |   +-- train_pipeline.py
|   +-- utils/
|   |   +-- data_utils.py
|   +-- train.py
```

## Download dataset
We will use Titanic dataset from Kaggle:
[Titanic Dataset](https://www.kaggle.com/c/titanic/data)

Save train.csv as: mlops-course/src/data/titanic.csv

**train_pipeline.py**

```python
import os
import joblib

import pandas as pd
from scikit.model_selection import train_test_split
from sklearn.ensemble import RandomForestClassifier
from sklearn.metrics import classification_report

from src.utils.data_utils import preprocess_data

def run_pipeline(data_path: str):
    print("[INFO] Loading dataset ...")
    df = pd.read_csv(data_path)

    print("[INFO] preprocessing dataset...")
    X, y = preprocess_data(df)

    print("[INFO] splitting dataset...")
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

    print("[INFO] training model...")
    model = RandomForestClassifier(n_estimators=100, random_state=42)
    model.fit(X_train, y_train)

    print("[INFO] evaluating model...")
    preds = model.predict(X_test)
    report = classification_report(preds)
    print(report)

    os.makedirs("src/models", exist_ok=True)
    joblib.dump(model, "src/models/titanic_model.pkl")
    print("[INFO] model saved to src/models/titanic_model.pkl")
```

**data_utils.py**

```python
```
