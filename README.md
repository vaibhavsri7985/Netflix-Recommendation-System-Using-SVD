# Netflix-Recommendation-System-Using-SVD

Movie Recommendation System using SVD
This project implements a Movie Recommendation System using Singular Value Decomposition (SVD) to predict ratings and recommend movies to users based on their past interactions. The system employs collaborative filtering to suggest movies that a user might enjoy, even if they haven't rated them yet.

Table of Contents
Data Preprocessing

Collaborative Filtering with SVD

Model Evaluation (CV)

Model Training

Rating Prediction

Recommendation Sorting

User-Centric Output

Model Capabilities

1. Data Preprocessing
The dataset was cleaned to ensure the quality and relevance of the recommendations.

Movies that were rated less frequently were removed from the dataset to prevent the model from recommending movies with fewer ratings, which may lead to inaccurate predictions. This process helps the system focus on popular and well-rated movies, ensuring more reliable and relevant recommendations.

In addition, users who rated fewer movies were also removed. This step ensures that the model is trained on users who have interacted with enough movies to generate meaningful preferences, preventing sparse data from affecting the predictions.

2. Collaborative Filtering with SVD
Singular Value Decomposition (SVD) was used as the collaborative filtering technique for this recommendation system.

SVD is effective in identifying hidden relationships between users and movies, allowing the model to provide personalized recommendations by learning latent factors that represent user preferences and movie characteristics.

3. Model Evaluation (CV)
Cross-validation (CV) was performed to evaluate the performance of the SVD algorithm by calculating the RMSE (Root Mean Square Error) and MAE (Mean Absolute Error) over 3 folds.

This evaluation was done only on the first 100,000 rows of the dataset to speed up the process and get an initial sense of how well the model performs before training it on the full dataset.

Evaluation Results:

RMSE (test set) for each fold:

Fold 1: 1.0014

Fold 2: 0.9999

Fold 3: 0.9944

Mean RMSE: 0.9986 (with a standard deviation of 0.0030)

MAE (test set) for each fold:

Fold 1: 0.7928

Fold 2: 0.7883

Fold 3: 0.7907

Mean MAE: 0.7906 (with a standard deviation of 0.0018)

Fit Time (training time):

Fold 1: 1.81 seconds

Fold 2: 1.92 seconds

Fold 3: 1.80 seconds

Mean Fit Time: 1.85 seconds

Test Time (prediction time):

Fold 1: 0.52 seconds

Fold 2: 0.45 seconds

Fold 3: 0.44 seconds

Mean Test Time: 0.47 seconds

The CV results suggest that the SVD algorithm performs consistently well with an average RMSE of 0.9986, and MAE of 0.7906, showing the model's stability across different subsets of the data.

4. Model Training
After performing cross-validation on the first 100,000 rows, the model was trained on the entire dataset to capture all the latent factors and interactions in the full dataset. This allows the model to make more accurate predictions based on a larger pool of user and movie data.

The model was trained using Singular Value Decomposition (SVD), which decomposes the large matrix of user-item interactions into three smaller matrices. These matrices help the algorithm predict missing values (ratings) by using learned patterns.

5. Rating Prediction
The model predicts ratings for movies that the user has not yet rated.

This step provides personalized movie recommendations by suggesting movies based on the predicted ratings, tailored to the user’s preferences.

6. Recommendation Sorting
Once the ratings were predicted, they were sorted in descending order.

This sorting ensures that the top 10 movie recommendations are the ones the model predicts the user would most likely enjoy based on their past ratings and preferences.

7. User-Centric Output
The final output of the system is a personalized list of movie recommendations for the user (in this case, user_712664).

These recommendations help guide the user’s movie choices and improve their overall experience with the platform by offering suggestions aligned with their viewing history.

8. Model Capabilities
The model is not limited to a single user. It can be used to predict movie ratings and provide recommendations for any user in the dataset.

By inputting a different user ID, the system can generate personalized movie recommendations for that user as well.


Conclusion
This recommendation system provides a user-centric movie suggestion experience by leveraging collaborative filtering with SVD. It predicts and recommends movies based on users' preferences, even for movies they have not rated, enhancing the overall movie selection experience. Additionally, removing less active users and less rated movies ensures the recommendations are more relevant and personalized. The cross-validation (CV) evaluation further validates the effectiveness of the model by consistently showing good performance in RMSE and MAE metrics.

Let me know if any further adjustments are needed!


