# Capstone: Predicting Pharmaceutical Sales in South Korea
### Analyze data, make connections, train and test models, and deploy! 

Following the tumultuous age of COVID-19 and the resulting restructuring and restoration of modern society, medical data and its potential predictive qualities have become increasingly valuable for studies of disease and disease control, medical procedures, travel, and more. 

This project aims to take a deeper look at some potential predictors for the total sales of pharmaceutical drugs in South Korea, analyzing data from different sectors of Korean society. The goal is therefore to find connections between these varying sources of data and use them to accurately predict Korean drug sales. 

**Note**: The final model will use a REST API and Docker container to be deployed to the web. The model used in this step will be pre-trained based on the 'Preprocessed_Data' available in the file. This means that currently additional training is not possible through the web, but can instead be added in a later implementation. 

The process can be simplified to the following workflow:
<br>Initial idea and data -> Analyze for connections -> Extract features -> Modeling and model evaluation -> Model deployment
<div>
<img src="Data/capstone_workflow.jpg" width=1000/>
</div>

## Project Overview:
<ins>Problem:</ins> Predict drug sales in Korea using data from various facets of South Korean life, including (but not limited to): weather, healthcare, travel, building construction, etc.
<br><br><ins>Topics:</ins> 
* Data analysis: EDA and feature extraction; recursive feature elimination and correlation studies
* Modeling: Basic regressors, tree-based algorithms, neural networks, ensembling, boosting
* Metric evaluation and analysis; optimization and best-model selection
* Model Deployment: create REST API for the final model, containerize and push to Docker container for deployment

Access the model: 
<br>[Initial project proposal](https://docs.google.com/document/d/1n_RRZgfwl0WT2p3aCEYIY8RU9nsb2mGosM1jT3U_WT0/edit)
<br>[Full project write-up](https://docs.google.com/document/d/10khUmjzLq3PH_gnmZfJjBF86JT7S8hG7s1BtfL9th5A/edit)
