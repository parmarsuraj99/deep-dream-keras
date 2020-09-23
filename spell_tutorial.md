# Deep Dream - Dreaming with a Neural Network in Keras

First introduced by Alexander Mordvintsev from Google in July 2015, **Deep Dream** is a technique that visualizes the patterns learned by a neural network. 

It does so by maximizing the activations of specific layer(s) for a given input image by running gradient ascent over it.

Original image             |  Image with patterns
:-------------------------:|:-------------------------:
![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/inputs/sky.jpg)  |  ![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/results/sky_dream.jpg)


The idea is to maximize the loss such that the image increasingly activates the selected layers. Base on the CNN model, it is generally seen that shallow layers focus more on low-level patterns like lines and abstract geometrical patterns. Deeper layers however, focuses more on the image patterns that it was trained on. We can use this findings to select the layers and get different outputs.

## Overview

The following tutorial uses a pre-trained Convolutional Neural Network model called "[InceptionV3](https://keras.io/api/applications/inceptionv3/)" from tf.keras .

Code for the tutorial [parmarsuraj99/deep-dream-keras](https://github.com/parmarsuraj99/deep-dream-keras)

We'll use **Spell Runs** to run a script from the code repository that takes an image and saves an image after applying the deep dream algorithm.

The repo already contains some sample input images that we can use for initial explorations.

## Let's dream



```shell
$ spell run --machine-type CPU \
    --pip matplotlib \
    --pip numpy \
    --pip opencv-python \
    --pip tensorflow_gpu==2.3.0 \
    --pip tqdm \
    'python src/dream.py \
        --src_img inputs/sky.jpg \
        --result_img results/sky_dream.jpg'
```

You'll see the run verbose like this. 


```shell
model loaded
Dreaming
('results', 'aus_dream.jpg')
(457, 685)
(326, 489)
Processing octave 0 with shape (326, 489)
... Loss value at step 1: 0.41
... Loss value at step 2: 0.62
    ...
    ...
... Loss value at step 8: 3.54
... Loss value at step 9: 3.88
Total time: 46.362966537475586 s
✨ Run is saving
Scanning for modified or new files from the run
Saving '/spell/results/aus_dream.jpg
✨ Run is pushing
Saving build environment for future runs
✨ Total run time: 1m25.039473s
✨ Run 41 complete

```

Note: If your run is killed, try using a smaller image.

## Uploading and mounting an image

This was done using a default image, but you might want to experiment with your image. You can upload them using spell and mount while running the script.

```shell
$ spell upload -n deep_dream inputs
```

Uploads can be easily mounted before starting a run.

![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/spell_images/uploads.png)

```shell
python src/dream.py \
    --src_img /spell/flowers_pixel.jpg \
    --result_img results/flower_dream.jpg
```

Here's a result of one of my uploaded pictures

![](https://raw.githubusercontent.com/parmarsuraj99/deep-dream-keras/master/results/flowers_pixel_dream.jpg)
