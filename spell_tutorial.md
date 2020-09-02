# Deep Dream - Dreaming with a Neural Network in Keras

First introduced by Alexander Mordvintsev from Google in July 2015, **Deep Dream** is a technique that visualizes the patterns learned by a neural network. 

It does so by maximizing the activations of specific layer(s) for a given input image by running gradient ascent over it.

Original image             |  Image with patterns
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/inputs/aus.jpg)  |  ![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/results/aus_dream.jpg)


The idea is to maximize the loss such that the image increasingly activates the selected layers. Base on the CNN model, it is generally seen that shallow layers.

## Overview

The following tutorial uses a pre-trained Convolutional Neural Network model called "[InceptionV3](https://keras.io/api/applications/inceptionv3/)" from tf.keras .

Code for the tutorial [parmarsuraj99/deep-dream-keras](https://github.com/parmarsuraj99/deep-dream-keras)

We'll use **Spell Runs** to run a script from the code repository that takes an image and saves an image after applying deep dream.

The repo already contains some sample input images that we can use for initial explorations.

## Let's see a dream