# Audio-Classification-using-CNN
## Multi class audio classification using Deep Learning (CNN, MLP)

### Project Objectives: 
The objective of this project is to build a multi class classifier to identify sound
of animals or noise.

### Dataset Description:
Dataset contained animal classes and their respective calling. Each audio sample is approximately about 2 sec long and has 44,100 amplitude samples/sec.


### Audio Data Preprocessing:

Audio dataset given has very high frame rate, on an average every file had 80,000 frames (amplitude/sec). With frames/sec being so high we have a lot of data and it needs some preprocessing. 

### Using ANN

During initial experiments ANN was not performing good and later after several experiments a Multi Layer Perceptron (MLP) model was build based on intuition of CNN. Before we feed audio data in network it was max pooled in 3 different layers and output of pooled layers was given input to the fully connected layers as shows in below figure. To merge features extracted from different pooling layers output of fully connected layer was merged.


#### Performance: 

Training was done for 500 epochs using Adaptive Moment Estimation (adam) as optimizer with learning rate of 0.0003.

|            | Training           | Testing        |
|-----| ------------- |:-------------:|
|Accuracy   | 91.11%      | 88.25%       |


### Using CNN

A network using Convolution layers was used to build classifier. The number of filters for both convolution was 64 and filter_size was 10 and 3 for respective layers followed by 3 fully connected layers, details about activation function used is in code. Max pooling was used after each convolution layer. During training over fitting was observed, to handle that dropout of 50% (keep) was used after first two fully connected layers and also ‘L2’ regularization was added to both layers. Input length was fixed as 22,000 with 1 channel. 


#### Performance: 

Training was done for 500 epochs using Adaptive Moment Estimation (adam) as optimizer with learning rate of 0.0001. 


|            | Training           | Testing        |
|-----| ------------- |:-------------:|
|Accuracy   | 99.88%      | 99.45%       |
