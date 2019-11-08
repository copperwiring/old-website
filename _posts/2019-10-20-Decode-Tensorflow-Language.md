---
layout: post
title: "Decoding Tensorflow"
date: 2019-11-06 01:25:06 -0700
comments: true
tags: technical
---

Tensorflow is now being used significantly for machine learning modelling, training and testing purposes. However, for someone who may have never used TensorFlow before or for people who love to understand the details behind the meanings of the commands and keywords, it may be toime consuming. This blog post is intended for people who may want to dive deep into what the commands stand for in the first place.

For covenience, we will take the standard example of a CNN demonstrated on the official website [here]("https://www.tensorflow.org/tutorials/images/cnn") . We will go through them step by step and decode what lies behind these lines. You can also read this blog while trying to using the colab [here]( https://colab.research.google.com/github/tensorflow/docs/blob/master/site/en/tutorials/images/cnn.ipynb)

# Importing TensorFlow

```
from __future__ import absolute_import, division, print_function, unicode_literals
import tensorflow as tf
from tensorflow.keras import datasets, layers, models
import matplotlib.pyplot as plt
```

# Downloading and working with CIFAR Dataset

```
(train_images, train_labels), (test_images, test_labels) = datasets.cifar10.load_data()
```

# Normalize pixel values to be between 0 and 1
```
train_images, test_images = train_images / 255.0, test_images / 255.0
```

# Verification of the Data
```
class_names = ['airplane', 'automobile', 'bird', 'cat', 'deer',
               'dog', 'frog', 'horse', 'ship', 'truck']

plt.figure(figsize=(10,10))
for i in range(25):
    plt.subplot(5,5,i+1)
    plt.xticks([])
    plt.yticks([])
    plt.grid(False)
    plt.imshow(train_images[i], cmap=plt.cm.binary)
    # The CIFAR labels happen to be arrays, 
    # which is why you need the extra index
    plt.xlabel(class_names[train_labels[i][0]])
plt.show()
```

# CNN Architecture
```
model = models.Sequential()
model.add(layers.Conv2D(32, (3, 3), activation='relu', input_shape=(32, 32, 3)))
model.add(layers.MaxPooling2D((2, 2)))
model.add(layers.Conv2D(64, (3, 3), activation='relu'))
model.add(layers.MaxPooling2D((2, 2)))
model.add(layers.Conv2D(64, (3, 3), activation='relu'))
```
