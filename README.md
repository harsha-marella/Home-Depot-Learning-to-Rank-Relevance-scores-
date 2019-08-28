# Home Depot Product Search Relevance (Learning to Rank)
<li> Learning to rank refers to machine learning techniques for training the model in a ranking task.  </li>
<li> In this project we have explored how an LETOR (Learning to Rank) is implemented on the Dataset having Categorical attributes which describes the Product Info and User queries to predict the Relevancy Scores. </li>
<li> Tokenization is Performed on the Product Titles and Descriptions. The tokens obtained are filtered by keeping Alphabetical tokens and removing Stop words/ Most common words. </li>
<li> Morphological/Root forms of tokens are obtained by implementing Porter Stemmer</li>
<li> The TF_IDF values of each token in a Document is Computed. Along with this the Associations of each token with other tokens are also computed. </li>
<li> Feature Engineering is implemented to generate the Similarity measures such as Cosine, Jaccard, Dice, Dot Product of product and queries. Along with this Statistical features such as product length, query length, Common words ratio with respect to both query and Product is also computed.</li>
<li>Even though the Similarity Features are statistically good enough to train the Regression Model, the reason for generating Statistical features is because as the Dot product is the numerator for every similarity measure the similarity values will be greater than zero only if Dot product > 0 indicating the strong correlation between them which will lead to Overfitting of the Model. Hence to overcome that problem Statistical Features are also generated. </li>
<li> To improve the efficiency of the Model the User queries were expanded using WordNet, Correlated words, Mutual Information. With these expanded queries Similarity and Statistical features are generated. </li>
<li> By analyzing the Correlation Matrix of these features we observed that there is statistically significant correlations between the features. This correlation will lead to Overfitting of the Model. </li>
<li> In order to overcome this issue PCA is implemented so that the components will be orthogonal i.e. uncorrelated. </li>
<li> Finally Regression Models such as Random Forest Regressor, Gradient Boosting Regressor, Nearest Neighbour Regressor and Ridge Regressor is trained on the PCA generated features to predict the Relevance scores. </li>
<li> Hyper parameter tuning is Performed on these models and the Optimal Parameter Configuration is determined by analyzing the error plots. And out of all Random Forest Regressor has performed well on the Test data with low RMSE at 0.49097. </li>
<li> Finally, Ensembled Learning is performed on the Random Forest and with the Optimal number of estimators the Test RMSE is reduced to 0.48614.
