# CS220-Project
CS220 Final Project

### Running a Notebook

1. Open either of the notebooks in Google Colab.
2. Run all cells sequentially from top to bottom.
3. Allow each cell to complete.
4. Wait for all cells to finish before reviewing results.
5. The output is a downloadable CSV file of the final AUC results.

--------------------
Report

Differentiating Fake vs Real news using Machine Learning

Nicko Martinez, Joshua Barsky

--------------------

Motivation
How does one differentiate between Real and Fake news in today's world? Years ago, official journalists who were well vetted were the core producers of mainstream articles. These days, although official journalists still run the show, many independent journalists have gained a large following on both independent news websites and social media. This has been a positive shift in the aspect of decentralizing news outlets, though the negative effects are an increasing number of journalists can occasionally spread fake news, which can sometimes be difficult to discern from the truth. In this work, we explore the idea of using language and patterns of known Real and Fake news articles and feeding this data into a Machine Learning model, XGBoost, to see if we can find reliable results in measuring the probability of how real or fake an article can be based entirely on its text.

--------------------

Section 1 - Dataset, Experiment Framework, and Evaluation
We begin by deciding which datasets we want to evaluate. Using only the text of online news articles gives a reliable dataset of a title and main body that can be found on all news articles. We therefore don't need to worry about data points that may or may not be appended to the data of any newly posted articles like publishing date, authors, view count, downloads count, an arbitrary point system, or any other unreliable form of data we can simply discard. We decided on using the WELFake dataset from Kaggle, since there are over 72,134 news articles available, with 35,028 real and 37,106 fake news.

The experiment framework consists of the evaluation of TF-IDF, Engineered writing-style features, and looking at the combination of the two. We keep the train/test split, model, and evaluation metric fixed in order to base our observations entirely on the changes of the feature set. The evaluation of these articles is based entirely on the Area Under ROC Curve (AUC) metric, which essentially does a measurement of how well our classifier separates the two classes of real and fake news. When the AUC is measured to be 1.0, separation is perfect. An AUC measure of 0.5 is representable as a random guess.

--------------------

Section 2 - Loading the data, Feature engineering, Baseline model
The data set that we settled on is the Welfare dataset, which contains over 72,000 articles that we were able to use to train our model. The basis of this decision is on the amount of data that is given, and the simplicity of the data being the Title, Article, and indicator of real or fake. Our testing was focused on running TF-IDF against feature engineering. TF-IDF gives a rating of the importance of a word over several sources, while feature engineering is a method of analyzing and taking characteristics, patterns, and phrases from text. Our baseline model of TF-IDF and its AUC was our original goal to attain with our feature engineering.

--------------------

Section 3 - Results and Analysis

The results of the experiment show a noticeable difference between the evaluated feature sets. The TF-IDF baseline attained an AUC score of approximately 0.65, while the engineered writing-style features attained an AUC score of approximately 0.89. Interestingly, combining the TF-IDF and engineered features only attained an AUC score of approximately 0.67. We then evaluated individual engineered features and combinations of engineered features using AUC as the primary metric. Features relating to article length, sentence structure, punctuation usage, capitalization, and vocabulary diversity consistently appeared in the strongest-performing combinations. The best combinations attained AUC scores of approximately 0.87, indicating that the language and patterns used in an article may be a strong indicator of whether that article is real or fake.
