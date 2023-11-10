Capstone Project EDA and Results




###  Predicting Songs that will be at the top 20 in the Apple’s Playlist
**Author: Julia Zhu**
#### Executive summary
In this project, we utilize a Kaggle dataset to predict whether a song will secure a spot in the top 20 on Apple’s playlist chart, along with predicting its ranking. For the regression task of predicting the song’s rank, we employ two constrained variants of the polynomial/linear regression tool—Lasso—and feature selection. In the classification aspect, determining whether a song will make it to the top 20 list, we employ Linear Regression, SVC, Decision Tree, and KNN. As a hybrid approach, we also leverage Lasso and Sequential Linear Regression to predict the song's ranks, with the target being inclusion in the top 20 or not.
Our findings reveal that KNN emerges as the best classifier for predicting the top 20 rank, achieving an impressive 84% accuracy with only 500 samples. Lasso, on the other hand, outperforms in predicting the song’s rank compared with  the sequential feature selector. Additionally, we observe that the prediction of song ranks can be enhanced with more data. The Hybrid approach proves highly effective, Sequential feature selection regression achieving predictions with an MSE of 0.14, translating to a 7% error rate for predicting whether the song is on the top 20 list.




#### Rationale
Why should anyone care about this question?
Predicting song ranks and/or what the top songs has crucial implications for the music industry, marketing, and culture. It's not just about commercial success; it influences artistic trends, decision-making, and economic outcomes.
The music industry is massive, with a projected US$10.33 billion revenue in 2022 and an expected annual growth rate of 10.41%. Predicting ranks is very valuable for:
Musicians and Concerts: Influencing song selection for live performances.
Awards and Recognition: Providing insights into potential award-winning songs.
Business and Revenue: Impacting sales, streaming, and revenue generation.
Emerging Artists: Guiding new artists on breaking into the industry.
Fan Engagement: Essential for engaging fans and communities.
Media Industry: Influencing song choices in films, commercials, and TV shows.
Cultural Preservation: Serving as a historical record of music culture.
Moreover, music is a powerful reflection and influencer of culture. The recent release of the "Taylor Swift" movie exemplifies this. Teen girls attending in sparkling dresses highlight the symbiotic relationship between music and culture. This cultural phenomenon is likely to impact music trends and ranks in the coming months.
#### Research Question 
Predict songs ranks in apple’s playlist
Predict the song will be in the top 20 on the apple’s playlist

#### Data Sources
Data source:  https://www.kaggle.com/datasets/sveta151/spotify-top-chart-songs-2022 
​​This dataset provides a list of all songs that have appeared in a weekly Spotify top chart.
Dataset provides name of the song, artist, URI, peak rank in the top charts that this song got, number of weeks on chart and main features of the song such as danceability, energy etc


#### Methodology
What methods are you using to answer the question?
For classification  I employed classification models, including Decision Tree, SVC, Logistic Regression, and KNN. Utilizing GridSearch, I identified the optimal model and hyperparameters for the task.
For non-classification—predicting ranks: I opted for LASSO linear Regression, sequential feature selection regression with poly degree of 3, and a hybrid approach.
 In the hybrid approach, I utilized the "digitized rank" (whether it is in the top 20) as the target and employed LASSO and sequential feature prediction to forecast the rank.
#### Results
  Summary of results:  
 1. for the classification, KNN with n=7 produced the best/most efficient results 

    Model and their best parameters
KNN ( Best_n = 7)
LGR (best model and param: sag, 0.1)
SVC (best model and param: linear,  0.1)

 knn_score_train is  0.848
lgr_score_train is  0.8266666666666667
svc_score_train is  0.84

- knn_score_test is  0.84
lgr_score_test is  0.792
svc_score_test is  0.84
DT Test score is 0.2

- knn_training_time  0.001417398452758789
 lgr_training_time 0.021414995193481445
SV_training_time  68.99942111968994

2. For prediction of songs,  The lasso and Sequential -feature selection worked similarly for the randomly selected 500 samples.  With the full sample size, Lasso was able to reduce the MSE further,, while sequential did not change as much.
   
500 samples_training MSE
Lasso: 733.3083531677235
Sequential feature: 1915.6558261761124

500 samples_testMSE
Lasso: 2848.2485754424715
Sequential feature: 2796.2627106386744

Full (953)samples_training MSE
Lasso: 1163.0087944113584
Sequential feature: 1980.5242989189271

Full (953) samples_test MSE
Lasso: 1575.8814003712062
Sequential feature:2424.810751857526




 3: I also use the lasso and sequential with full data set and was able to to predict 
 if the song was in the top 20 quite accurately.    Error rate = 0.14/20 = 7% 


Training_MSE
Lasso: 0.22360512832584012
Sequentia: 0.14535023376759143

Test_MSE
Lasso: 0.22966062296606235
Sequentia: 0.1540730342275059

error rate translate to 
0.15/20 = 7.5%



#### Next steps
What suggestions do you have for next steps?
The classification with GridSearch was limited to the sample size due to computing resource constraints. We could attempt to secure a larger computing resource to test whether we can further improve performance.
The regression was able to run with the full dataset and demonstrated performance improvement compared to the limited dataset. Exploring the possibility of obtaining even more data could facilitate continued improvement.
The Hybrid approach was particularly intriguing, providing strong predictions for the top 20 rank with the constrained linear regression.

#### Outline of project
- [Link to notebook 1]() https://github.com/Ljuliazhu/test2-0707/blob/main/spotify_EDA_results_10_10--Latest.ipynb 
##### Contact and Further Information
If you have any questions, please email me at zhu.julia.2010@gmail.com
    

