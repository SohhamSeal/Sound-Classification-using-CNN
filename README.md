# Whose voice was that?
## Multi class audio classification using Deep Learning

### Project Objectives: 
The objective of this project is to build a multi class classifier to identify sound
of animals or noise.

### Audio Data Preprocessing:

Audio dataset given has very high frame rate, on an average every file had 80,000 frames (amplitude/sec). With frames/sec being so high we have a lot of data and it needs some preprocessing. 

![audio_preprocessing-1](https://user-images.githubusercontent.com/77045044/182619587-99dc553a-ce26-4141-8b1a-eff38925a489.png)

### Using ANN

During initial experiments ANN was not performing good and later after several experiments a Multi Layer Perceptron (MLP) model was build based on intuition of CNN. Before we feed audio data in network it was max pooled in 3 different layers and output of pooled layers was given input to the fully connected layers as shows in below figure. To merge features extracted from different pooling layers output of fully connected layer was merged.

![ANN_Net_2-1](https://user-images.githubusercontent.com/77045044/182619056-2e7a66e6-148c-4141-aae6-38edcc9f9000.png)

#### Performance: 

Training was done for 500 epochs using Adaptive Moment Estimation (adam) as optimizer with learning rate of 0.0003.

|            | Training           | Testing        |
|-----| ------------- |:-------------:|
|Accuracy   | 91.11%      | 88.25%       |


### Using CNN

A network using Convolution layers was used to build classifier. The number of filters for both convolution was 64 and filter_size was 10 and 3 for respective layers followed by 3 fully connected layers, details about activation function used is in code. Max pooling was used after each convolution layer. During training over fitting was observed, to handle that dropout of 50% (keep) was used after first two fully connected layers and also ‘L2’ regularization was added to both layers. Input length was fixed as 22,000 with 1 channel. 

![CNN_Net-1](https://user-images.githubusercontent.com/77045044/182619414-e20ba6a5-9969-40fc-87b7-190e3c07d638.png)

#### Performance: 

Training was done for 500 epochs using Adaptive Moment Estimation (adam) as optimizer with learning rate of 0.0001. 


|            | Training           | Testing        |
|-----| ------------- |:-------------:|
|Accuracy   | 99.88%      | 99.45%       |
