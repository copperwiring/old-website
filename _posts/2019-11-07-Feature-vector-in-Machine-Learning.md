---
layout: post
title: "Feature Vector in Machine Learning"
date: 2019-11-07 22:21:06 -0700
comments: true
tags: technical
---


In computer vision we keep referring to feature vector, especially when we talk about CNNs. But what exactly is a feature vector and can how can you visualize it?
Imagine we have an RGB image is the form as shown below:

<img src="/images/rgbchannel.png " width="150" height="120" />

Notice, that the value are unique for each color channel. However, we don’t intend to send out this data to any algorithm in 3 fold i.e. sending for one channel and doing computation, sending for second and so on. This is very unrealistic from computation point of you because our original data (pixel values) are ‘together’ representing the image. Hence, we create what we call a feature vector. We create 1-D column vector with values from these 3 color channels. For instance, we start from Red channel and bread each value row wise till the last value. Next we do the same for Blue channel and lastly for Green channel. This gives us one single column vector representing the original image in the form of, what we call, ‘feature vector’. So, what is the final size of the feature vector? This is important to know the total amount of data we will eventually use to do any computation.

When we see the CNN structure, we see that the architecture is defined usingm x n x 3, in case of RGB images. For example, a CNN architecture of dimension 64 x 64 x 3 will have a feature vector of size 12,288.

Simple!
