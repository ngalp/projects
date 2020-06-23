# Python projects

This repository contains python projects which had been submitted as part of course requirements for NYP SD-BBDA conducted in 2018/2019.

### (1) Predicting HDB resale prices with sci-kit learn ###
For this project, the aim is to predict HDB resale prices, taking into account 
```
1. property inherent characteristics such as tenure, floor area, floor level, etc,
2. location inherent characteristics such as market segment, property district, and 
3. proximity to amenities such as MRT stations, primary schools, hawker centers and markets.
```
This project was done solely in Python, while achieving the same data and modelling objectives when multiple applications were required previously*. The code includes data exploration and cleaning/ preparation steps. Of note is the use of shapely and geopy for geospatial plotting and proximity computation from longitude and latitude data.

(*For a previous module/ project, three yr private property transaction data was obtained via URA Data Service API, geographical data analysed in QGIS (to obtain distances from/ proximity to amenities), data prepared in Excel Power Query and predictive model built in Rapidminer to predict private property resale prices.) 

<ins>Link to Python Notebook</ins>

* <a href="https://github.com/ngalp/projects/blob/master/hdb_retrievedata.ipynb">Part 1. ETL</a>
* <a href="https://github.com/ngalp/projects/blob/master/hdb_analysedata.ipynb">Part 2. Analysis and Predictive Modelling</a>


### (2) Sentiment analysis on restaurant reviews with NLTK and TextBlob ###

For this project, the aim is to predict sentiment of a review using sentiment analysis. From there, key topics/ area are identified for each sentiment class. With this, positive areas and room-for-improvement areas can be identified from the reviews by applying topic modelling using LDA or similar analysis to identify key topics/ area within each sentiment class. 

The project included web scraping of more than 450,000 restaurant reviews of 1,7k restaurants using a combination of beautiful soup and selenium (code and output file stored in local is not uploaded to github). The code include feature generation, data cleaning (including lemmatization, tokenization, contractions, stopword removal etc). CountVectorizer and TFIDFVectorizer were used to create word vector on the training data. Finally predictions were conducted for each of the word vectors using Logistic Regression, Support Vector Classifier, Decision Tree Classifier, Random Forest Classifier and Multinomial Naive Bayes. Topical representation was visualised in a word cloud. The data sources and sentiment analysis were also visualised using Qliksense (results not uploaded to github)

<ins>Link to Python Notebook</ins>

* Part 1: Web-scraping review data (The code for this is not uploaded to github)
* <a href="https://github.com/ngalp/projects/blob/master/restaurant_explore.ipynb">Part 2: Explore the data</a>
* <a href="https://github.com/ngalp/projects/blob/master/restaurant_preprocess.ipynb">Part 3: Prepare the data (pre-processing)</a>
* <a href="https://github.com/ngalp/projects/blob/master/restaurant_cv.ipynb">Part 4a: Modelling using word vector generated from CountVectorizer</a>
* <a href="https://github.com/ngalp/projects/blob/master/restaurant_tv.ipynb">Part 4b: Modelling using word vector generated from TDIDFVectorizer</a>
* <a href="https://github.com/ngalp/projects/blob/master/restaurant_sentiment.ipynb">Part 5: Summary Results with Topics Identified</a>

### 3. Predicting Customer Purchases using Machine Learning ###
For this project, the aim is to predict purchases using the target field TargetBuy (0, 1). The code includes data exploration and cleaning/ preparation steps. Modelling is then performed with various sklearn (scikit-learn) models listed below, as well as exploration of whether <a. Target Class Balancing using SMOTE (Synthetic Minority Oversampling Technique)> and <b. Dimensionality Reduction with PCA> have a positive impact on the prediction results. Grid-search is then performed on selected well-performing models. The final model(s) are applied to the test data.

<a href="https://github.com/ngalp/projects/blob/master/predictive_model.ipynb"><ins>Link to Python Notebook</ins></a>


### 4. MNIST: Image Recognition ###
The MNIST is widely known as the 'Hello World' dataset for computer vision. Records have already been size-normalized and centered in a fixed-size image, thus useful to try out different machine learning techniques as minimal efforts are required on preprocessing and formatting.

<a href="https://github.com/ngalp/projects/blob/master/mnist.ipynb"><ins>Link to Python Notebook</ins></a>
