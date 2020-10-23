# Realtime Facial Expression Classification

This is a [Kaggle Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge)
The task is to categorize each face based on the emotion shown in the facial expression in to one of seven categories (Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral).


# summary first
Good performance achieved: 70% accuracy over private test data (kaggle provided). For comparison, the kaggle [private leaderboard](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/leaderboard) shows that 71% accuracy for the top rank and 69% accuracy fo the second rank.

# strategy sketch
- Two stage transfer learning 
- Class balacning 
- Label smoothing
- Hyper-parameter adjust ( dropout / learning rate )

### Transfer Learning


