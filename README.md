# Netflix-Recommender-System
**Introduction:**<br/>
Netflix is all about connecting people to the movies they love. To help customers find those movies, they developed world-class movie recommendation system: CinematchSM. Its job is to predict whether someone will enjoy a movie based on how much they liked or disliked other movies. Netflix use those predictions to make personal movie recommendations based on each customer’s unique tastes. And while Cinematch is doing pretty well, it can always be made better.<br/>

Now there are a lot of interesting alternative approaches to how Cinematch works that netflix haven’t tried. Some are described in the literature, some aren’t. We’re curious whether any of these can beat Cinematch by making better predictions. Because, frankly, if there is a much better approach it could make a big difference to our customers and our business.<br/>

Netflix provided a lot of anonymous rating data, and a prediction accuracy bar that is 10% better than what Cinematch can do on the same training data set. (Accuracy is a measurement of how closely predicted ratings of movies match subsequent actual ratings.)<br/>

**Objectives:**<br/>

1. Predict the rating that a user would give to a movie that he ahs not yet rated.<br/>
2. Minimize the difference between predicted and actual rating (RMSE and MAPE)<br/>

**Constraints:**<br/>

Some form of interpretability.<br/>

**Data:**<br/>

Data files :<br/>
combined_data_1.txt combined_data_2.txt combined_data_3.txt combined_data_4.txt movie_titles.csv<br/>

The first line of each file [combined_data_1.txt, combined_data_2.txt, combined_data_3.txt, combined_data_4.txt] contains the movie id followed by a colon. Each subsequent line in the file corresponds to a rating from a customer and its date in the following format:CustomerID,Rating,Date<br/>

MovieIDs range from 1 to 17770 sequentially.<br/>
CustomerIDs range from 1 to 2649429, with gaps. There are 480189 users.<br/>
Ratings are on a five star (integral) scale from 1 to 5.<br/>
Dates have the format YYYY-MM-DD.<br/>

**Performance Metric:**<br/>
Mean Absolute Percentage Error<br/>
Root Mean Squared Error<br/>

**Conclusion:**<br/>


|     Model      |      Train_rmse     |     Test_rmse      |
|---|---|
|   first_algo   |  0.8131655657201271 | 1.0736360638377618 |
|    bsl_algo    |  0.9408643608703676 | 1.0735808085059688 |
|    xgb_bsl     |  0.8206049195071748 | 1.073068397290458  |
|   knn_bsl_u    | 0.26375340495634786 | 1.0729740633728826 |
|   knn_bsl_m    | 0.20738563427680795 | 1.0729630032608906 |
|  xgb_knn_bsl   |  0.7634494751495742 | 1.086218472877775  |
|      svd       |  0.6486886147912374 | 1.0730035598473069 |
|     svdpp      |  0.5795854676897524 | 1.0730045699350494 |
|   xgb_final    |  0.8068454624363004 | 1.0734467307804618 |
| xgb_all_models |  1.0606454093218731 | 1.0752397685718569 |

