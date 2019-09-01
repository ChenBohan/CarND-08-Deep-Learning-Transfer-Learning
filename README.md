# CarND-08-Deep-Learning-Transfer-Learning

Udacity Self-Driving Car Engineer Nanodegree: Transfer Learning

## Further reading

- [Kaggle](https://www.kaggle.com/)

- Import a pre-trained network by using the [Keras Applications models](https://keras.io/applications/)

- [original research paper on AlexNet](https://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

## Guide for How to Use Transfer Learning

### Case 1: Small Data Set, Similar Data

- freeze all the weights from the pre-trained network

- train the network to update the weights of the new fully connected layer

### Case 2: Small Data Set, Different Data

- slice off most of the pre-trained layers near the beginning of the network

- freeze all the weights from the pre-trained network

- train the network to update the weights of the new fully connected layer

### Case 3: Large Data Set, Similar Data

- re-train the entire neural network

### Case 4: Large Data Set, Different Data

- retrain the network from scratch

- alternatively, you could just use the same strategy as the "large and similar" data case

## How to apply transfer learning?

Two popular methods:

1. Feature extraction. 

Take a pretrained neural network and replace the final (classification) layer with a new classification layer, or perhaps even a small feedforward network that ends with a new classification layer. 

During training the weights in all the pre-trained layers are frozen, so only the weights for the new layer(s) are trained. 

In other words, the gradient doesn't flow backwards past the first new layer.

2. Finetuning

This is similar to feature extraction except the pre-trained weights aren't frozen. The network is trained end-to-end.
