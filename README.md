# AI-Deep-Learning-05-Intro-to-Transfer-Learning
Udacity Self-Driving Car Engineer Nanodegree: Transfer Learning

## Guide for How to Use Transfer Learning

### Case 1: Small Data Set, Similar Data

Add a new fully connected layer that matches the number of classes in the new data set.

To avoid overfitting on the small data set, the weights of the original network will be held constant rather than re-training the weights. 

### Case 2: Small Data Set, Different Data

Add to the remaining pre-trained layers a new fully connected layer that matches the number of classes in the new data set.

The original training set and the new data set do not share higher level features. 

In this case, the new network will only use the layers containing lower level features.

### Case 3: Large Data Set, Similar Data

Remove the last fully connected layer and replace with a layer matching the number of classes in the new data set.

We can re-train all of the weights.

Because the original training set and the new data set share higher level features, the entire neural network is used as well.

### Case 4: Large Data Set, Different Data

Remove the last fully connected layer and replace with a layer matching the number of classes in the new data set.

If using the pre-trained network as a starting point does not produce a successful model, another option is to randomly initialize the convolutional neural network weights and train the network from scratch.

## How to apply transfer learning?

Two popular methods:

1. Feature extraction. 

Take a pretrained neural network and replace the final (classification) layer with a new classification layer, or perhaps even a small feedforward network that ends with a new classification layer. 

During training the weights in all the pre-trained layers are frozen, so only the weights for the new layer(s) are trained. 

In other words, the gradient doesn't flow backwards past the first new layer.

2. Finetuning

This is similar to feature extraction except the pre-trained weights aren't frozen. The network is trained end-to-end.
