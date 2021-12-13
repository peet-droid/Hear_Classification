# ECG_Heartbeat_Classification

Requirement : Keras, tensorflow, numpy 

# Heartbeat Classification : Detecting abnormal heartbeats and heart diseases from


An ECG is a 1D signal that is the result of recording the electrical activity of
the heart using an electrode. It is one of the tool that cardiologists use to
diagnose heart anomalies and diseases.

In this blog post we are going to use an [annotated
dataset](https://www.kaggle.com/shayanfazeli/heartbeat) of heartbeats already
preprocessed by the authors of [this paper](https://arxiv.org/abs/1805.00794) to
see if we can train a model to detect abnormal heartbeats.

### Model

Similar to [1] I use a neural network based on 1D convolutions but without the
residual blocks :

<span class="figcaption_hack">Figure 3 : Keras model</span>

Code :

### Results

MIT-BIH Arrhythmia dataset :

* Accuracy : **98.5**
* F1 score : **91.5**

The PTB Diagnostic ECG Database

* Accuracy : **98.3**
* F1 score : **98.8**

### Transferring representations

From Scratch :

* Accuracy : **98.3**
* F1 score :** 98.8**

Freezing the Convolution Layer and Training the Fully connected ones :

* Accuracy : **95.6**
* F1 score : **96.9**

Training all layers :

* Accuracy : **99.2**
* F1 score : **99.4**

We can see the freezing the first layers does not work very well. But if we
initialize the weights with those learned on MIT-BIH and train all layers we are
able to improve the performance compared to training from scratch.


