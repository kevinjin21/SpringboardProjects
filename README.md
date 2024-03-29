# Springboard Projects
### A collection of projects developed while enrolled in the UCSD ML bootcamp. Projects explore a variety of ML topics in real-world application frameworks.

The UCSD Machine Learning Course is a 6 month program intended to be used as a 'crash course' for learning machine learning. During this course, students are required to create a *capstone project*, which takes real-world data, and formulates a problem to solve or predict using machine learning algorithms and methods.

Aside from this capstone project, I have independently researched and developed a few other "passion projects", fusing topics I am personally interested in with techniques learned throughout the course. These 'mini-projects' vary in length and depth, but nevertheless each explore unique aspects of machine learning and data analysis.

A brief overview of the projects and relevant topics are as follows:

## [Capstone Project: Predicting Sales of Pharmaceutical Drugs in South Korea](https://github.com/kevinjin21/SpringboardProjects/tree/main/Capstone)
<u>Problem:</u> Predict drug sales in Korea using data from various facets of South Korean life, including (but not limited to): weather, healthcare, travel, building construction, etc.
<br>Topics: 
* Data analysis: EDA and feature extraction; recursive feature elimination and correlation studies
* Modeling: Basic regressors, tree-based algorithms, neural networks, ensembling, boosting
* Metric evaluation and analysis; optimization and best-model selection
* Model Deployment: create REST API for the final model, containerize and push to Docker container for deployment

[Access the model and AWS deployment](https://github.com/kevinjin21/SpringboardProjects/tree/main/Capstone/Pharm_Deploy)
<br>[Initial project proposal](https://docs.google.com/document/d/1n_RRZgfwl0WT2p3aCEYIY8RU9nsb2mGosM1jT3U_WT0/edit)
<br>[Full project write-up](https://docs.google.com/document/d/10khUmjzLq3PH_gnmZfJjBF86JT7S8hG7s1BtfL9th5A/edit)

## Projects
### [Ghibli Text Generation](https://github.com/kevinjin21/SpringboardProjects/tree/main/Ghibli%20Dialogue%20Generation%20Mini-Project)
<u>Problem:</u> Generate dialogue text in the style of renowned film studio, Studio Ghibli. 
<br>Topics:
* Pytorch 'long short-term memory network' (LSTM) using character chunks to predict future characters
* Data collection and manipulation, namely reshaping and creating tensors for analysis
* Pytorch LSTM construction and training

### [Disney+ Movie Recommendation](https://github.com/kevinjin21/SpringboardProjects/tree/main/Disney%20Recommendation%20Mini-Project)
<u>Problem:</u> Make recommendations for TV shows/movies from Disney's Disney+ streaming service based on user preferences.
<br>Topics:
* Data exploration and analysis: clean and analyse existing movie/TV data to be used for predictions
* TFIDF Vectorizer and cosine similarity used to make content-based recommendations
* Recommend related movies based on similarities in movie details and potential interests of user

### [Web Scraping Film Recommendation](https://github.com/kevinjin21/SpringboardProjects/tree/main/Animated%20Film%20Web%20Scraping%20Recommendation%20Mini-Project)
<u>Problem:</u> Scrape anime film data from 2022, 2023 off of Wikipedia webiste and build a simple recommendation system using the data available.
<br>Topics:
* Web scraping and HTML parsing; BeautifulSoup
* Data cleaning and analysis - focus on realistic, incomplete and inconsistent data
* Simple recommendation system comparing content similarities (cosine) 

### [Korea Surgery Time Series Prediction](https://github.com/kevinjin21/SpringboardProjects/tree/main/Health%20Data%20Mini-Project)
<u>Problem:</u> Predict cases of South Korean surgeries using time-series analysis of existing medical data.
<br>Topics:
* EDA of health data statistics; analyze existing trends in time series data
* Use auto ARIMA to train and predict future cases

