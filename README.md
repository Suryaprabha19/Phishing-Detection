# Phishing-Detection
This project aims to detect phishing websites using machine learning. It utilizes various features extracted from URLs and trains a CatBoost model to classify websites as either phishing or legitimate.

## Dataset

The project uses a dataset of URLs labeled as phishing or legitimate. The dataset is preprocessed to extract relevant features for training the model.

## Features

The following features are extracted from URLs:

- `use_of_ip`: Whether the URL contains an IP address.
- `abnormal_url`: Whether the URL is abnormal.
- `google_index`: Whether the URL is indexed by Google.
- `count.`: Number of dots in the URL.
- `count-www`: Number of "www" in the URL.
- `count@`: Number of "@" in the URL.
- `count_dir`: Number of directories in the URL.
- `count_embed_domian`: Number of embedded domains in the URL.
- `short_url`: Whether the URL is a shortened URL.
- `count-https`: Number of "https" in the URL.
- `count-http`: Number of "http" in the URL.
- `count%`: Number of "%" in the URL.
- `count?`: Number of "?" in the URL.
- `count-`: Number of "-" in the URL.
- `count=`: Number of "=" in the URL.
- `url_length`: Length of the URL.
- `hostname_length`: Length of the hostname.
- `sus_url`: Whether the URL contains suspicious words.
- `count-digits`: Number of digits in the URL.
- `count-letters`: Number of letters in the URL.
- `fd_length`: Length of the first directory.
- `tld_length`: Length of the top-level domain.

## Data Balancing

The dataset used in this project might have an imbalance between phishing and legitimate websites. This means that one class (e.g., legitimate websites) might have significantly more samples than the other class (e.g., phishing websites). Class imbalance can negatively impact the performance of machine learning models, as they might be biased towards the majority class.

To address this issue, this project employs a technique called **SMOTE (Synthetic Minority Over-sampling Technique)**. SMOTE is an oversampling technique that generates synthetic samples for the minority class to balance the class distribution. 

Here's how SMOTE works in this project:

1. **Identify the minority class:** In this case, phishing websites are likely the minority class.
2. **Generate synthetic samples:** SMOTE creates new synthetic samples for the minority class by interpolating between existing minority class samples. This helps to increase the number of minority class samples and balance the dataset.
3. **Train the model:** The model is trained on the balanced dataset, which now has a more equal representation of both phishing and legitimate websites.

By using SMOTE, this project aims to improve the model's ability to detect phishing websites and reduce the bias towards the majority class.  

## Model

The project uses a CatBoost, XGBoost, Random Forest, Logistic Regression, Decision Tree, KNN model for classification. The model is trained on the extracted features and evaluated on a test set.
