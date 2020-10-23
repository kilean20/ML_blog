# Realtime Facial Expression Classification

This is a [Kaggle Challenge](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge).

The task is to categorize each face based on the emotion shown in the facial expression in to one of seven categories (Angry, Disgust, Fear, Happy, Sad, Surprise, Neutral).


# Performance
Good performance achieved: 70% accuracy over private test data (Kaggle provided). 

For comparison, the Kaggle [private leaderboard](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/leaderboard) shows that 71% accuracy for the top rank and 69% accuracy fo the second rank.

# Strategy toward good performance
- Two stage transfer learning 
- Class balacning 
- Label smoothing
- Hyper-parameter adjust ( dropout / learning rate )

#### Transfer Learning
Used ResNet50 architecture of [keras-VGGFace](https://github.com/rcmalli/keras-vggface) for the pre-trained base. 
```js
from keras_vggface.vggface import VGGFace
vggface = VGGFace(model='resnet50', include_top=False, input_shape = (224,224,3))
vggface.trainable = False
```
In the first stage, the pretrained model is forzen.

Although the Kaggle [data](https://www.kaggle.com/c/challenges-in-representation-learning-facial-expression-recognition-challenge/data) consists of single channel 48x48 size images, the pretrained model input size 224x224 is kept as it is so that pretrained latent features do not change. 

The top layers are constructed in the following way:
```js
model = Sequential([vggface,
                    Flatten(),
                    Dropout(0.25),
                    Dense(2048, activation='relu'),
                    Dropout(0.25),
                    Dense(1024, activation='relu'),
                    Dense(7, activation='softmax', name = 'classifer')])
```
After training about 20 epochs (at which the loss curve tend to flat), the pre-trained model is unfrozen (except the batch normalization layers) for the 2nd stage fine tune.
```js
for layer in model.layers[0].layers:
    if 'bn' not in layer.name:
        layer.trainable = True
```
