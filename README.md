# ML---Company-Bankruptcy-Kaggle
Get my notebook: https://colab.research.google.com/drive/1wEd7PtVP3I56hVY7JiSshlWjGvVelWl5?usp=sharing

I. Introduction: Research Question and Problem for Management

The company bankruptcy dataset consists of 95 attributes for 6819 companies. The purpose of this study is to determine how these attributes affect the likeliness of a company to go bankrupt. Analysis of the company bankruptcy data provides key information into whether or not a company may go bankrupt, which can help make financial and investment decisions. Investment firms can use this type of data to make decisions on whether or not they want to put money into a company. It can also help banks when deciding who to give loans to if a company is trying to expand. 

II. Analysis of Dependent Variable (Bankrupt - yes or no)

An initial analysis of the dependent variable 'Bankrupt?' shows that this data was not balanced, since there were far more not-bankrupt companies than there were instances of bankruptcy. 6599 companies were not bankrupt and only 220 were bankrupt. Those two categories were also labeled financially stable (96.77% of the dataset - not bankrupt) and financially unstable (3.23% of the dataset - bankrupt). In order to balance the number of bankrupt and not bankrupt data, the dataset was shuffled and split to include all bankrupt datapoints and the same amount (220 instances) of not bankrupt. This allowed for greater correlations between feature variables and the target variable (Bankrupt?) as can be seen in Figure 1. 

![image](https://user-images.githubusercontent.com/97359451/151726294-8e3f2c38-22c8-47f1-8174-fffcbe18a3e9.png)
Figure 1. Heatmap of entire dataset (above) versus heatmap of the balanced dataset (same number of bankrupt versus not bankrupt instances) (below). 

V. Correlations and Potential Predictors of Bankruptcy 

The top independent variables affecting bankruptcy include ROA(C) before interest and depreciation before interest, ROA(A) before interest and % after tax, ROA(B) before interest and depreciation after tax, net value per share (B), net value per share (A), net value per share (C), persistent EPS in the last four seasons, per share net profit before tax (Yuan), debt ratio percentage, net worth/assets, net profit before tax/paid-in capital, current liability to assets, retained earnings to total assets, total income/total expense, and net income to total assets. These features all had a correlation of at least 0.5 and were included in model testing versus the entire set of features (see figure 2). Relevant features were plotted against bankruptcy to visualize relationships (figure 3). 

![image](https://user-images.githubusercontent.com/97359451/151726726-7c9b6c26-d165-484f-b08f-739a2c403aab.png)
Figure 2. Heatmap of relevant features for later model testing. Correlation of at least 0.5. 

![image](https://user-images.githubusercontent.com/97359451/151726801-1f04c38e-c9a1-49bf-9d76-02c036e28ccd.png)
Figure 3. Plots of each relevant feature with a correlation at least 0.5 against bankruptcy target variable. 

VI. Models

The following models were tested with the data set split at 80/20: Logistic Regression, Naive Bayes, SVM, Random Forest Classifier, Gradient Boosted Trees, and Extra Tree Classifier. The models were fit to 80% of the training dataset and then used on the 'test' 20% remaining of the training dataset to predict bankruptcy. Each model was created for both the original dataset with all feature variables, and the subset of data that only included the list of relevant features found from the correlation matrix as noted above. A confusion matrix was created for each model and they were scored to determine which model was the best for this data. Extra tree classifier was found to be the best model for the dataset of relevant features. Extra tree classifier correctly predicted 93 percent of the test data (see Table 1 for all model stats and Figure 4 for ROC curve). 

Table 1. Statistics for all models tested on both the original dataset and the selected features dataset.
<img width="928" alt="Screen Shot 2022-02-06 at 6 15 28 PM" src="https://user-images.githubusercontent.com/97359451/152707796-cdf27f7e-733b-4c19-806a-7f42a738cee8.png">


![image](https://user-images.githubusercontent.com/97359451/152707849-7bd24dfa-9988-46f2-8a42-143219ab0df0.png)

Figure 4. ROC Curve of Extra Trees Classifier with Selected Features Dataset


VII. Conclusions

After EDA of the dataset, the factors to include in the machine learning model are those that have the greatest impact on likeliness for a company to go bankrupt. After testing several models, extra trees classifier performed the best on the training data (using train_test_split). After testing on both the original dataset and the dataset with only relevant features, extra trees classifier correctly predicted 93% of bankruptcy instances. This model can be used to determine how to invest in companies or give loans to companies. 
