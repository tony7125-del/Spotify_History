# Spotify Listening History Analysis

## Project Overview

This project analyzes Spotify listening history data to explore user listening patterns, identify popular artists and tracks, and build a simple machine learning model to predict listening duration (`ms_played`).

The notebook covers:

* Data cleaning and preprocessing
* Exploratory Data Analysis (EDA)
* Feature preparation
* Machine learning model training
* Model evaluation

---

# Project Objectives

The main goals of this project are:

1. Clean and prepare Spotify listening history data.
2. Explore user listening behavior.
3. Identify:

   * Most popular artists
   * Frequently played songs
   * Songs that are often skipped
4. Analyze relationships between replay behavior and listening duration.
5. Build a regression model to predict listening time (`ms_played`).
6. Recommend ways to improve the listening experience.

---

# Technologies Used

The following Python libraries were used in this project:

* `pandas` – Data manipulation and analysis
* `numpy` – Numerical operations
* `matplotlib` – Data visualization
* `seaborn` – Statistical visualizations
* `scikit-learn` – Machine learning and preprocessing

---

# Dataset

The dataset used is:

`spotify_history - spotify_history.csv`

The dataset contains Spotify listening history information such as:

* Artist name
* Track name
* Playback duration
* Skipped tracks
* Replay behavior
* Listening timestamps

---

# Project Workflow

## 1. Data Cleaning

The notebook begins by preparing the dataset through:

* Cleaning missing or inconsistent data
* Formatting columns
* Splitting and organizing relevant features

---

## 2. Exploratory Data Analysis (EDA)

Several analyses were performed to understand listening behavior:

### Key Analyses

* Checking the most popular artists
* Identifying the most played songs
* Determining which songs are skipped frequently
* Exploring relationships between replays and listening duration

These insights help understand user music preferences and engagement.

---

## 3. Feature Engineering

The project uses:

### TF-IDF Vectorization

`TfidfVectorizer()` was introduced to transform text-based features into numerical representations.

### Feature Selection

The target variable is:

```python
ms_played
```

Input features are created using:

```python
X = spotify.drop(['ms_played'], axis=1)
y = spotify['ms_played']
```

---

## 4. Train-Test Split

The dataset is split into training and testing sets:

```python
train_test_split(X, y, test_size=0.2, random_state=42)
```

* 80% Training Data
* 20% Testing Data

---

## 5. Machine Learning Model

A `LinearRegression` model was used because:

* `ms_played` is a continuous numerical variable.
* Regression models are suitable for predicting continuous values.

```python
model = LinearRegression()
```

The notebook currently uses boolean columns for training:

```python
X_train_numeric = X_train.select_dtypes(include=['bool'])
```

This was done to avoid errors caused by categorical and text features.

---

# Model Evaluation

The model performance was evaluated using:

## Mean Absolute Error (MAE)

Measures the average prediction error.

## R² Score

Measures how well the model explains the variance in listening duration.

```python
mean_absolute_error(y_train, y_pred)
r2_score(y_train, y_pred)
```

---

# Key Findings

The notebook aims to discover:

* Which artists are listened to the most
* Which songs users skip frequently
* Listening patterns over time
* User engagement with music playback

These insights can help improve music recommendations and user experience.

---

# Possible Improvements

This project can be improved further by:

* Encoding categorical variables properly
* Using advanced feature engineering
* Extracting time-based features from timestamps
* Using more advanced machine learning models such as:

  * Random Forest Regressor
  * XGBoost
  * Gradient Boosting
* Adding visual dashboards
* Improving recommendation logic

---

# How to Run the Project

## 1. Clone the Repository

```bash
git clone <repository-link>
```

## 2. Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

## 3. Open the Notebook

Run the Jupyter Notebook:

```bash
jupyter notebook Spotify_Listening_History.ipynb
```

---

# Future Work

Future enhancements may include:

* Personalized recommendation systems
* Deep learning models for music prediction
* Real-time Spotify API integration
* Interactive dashboards using Streamlit or Power BI

---

# Conclusion

This project demonstrates how Spotify listening history data can be analyzed using Python and machine learning techniques to better understand listening behavior and improve user music experiences.

The notebook provides a foundation for:

* Music recommendation systems
* User behavior analysis
* Predictive analytics in streaming platforms

---

# Author

Created as a Spotify Listening History Analysis and Machine Learning project using Python.
