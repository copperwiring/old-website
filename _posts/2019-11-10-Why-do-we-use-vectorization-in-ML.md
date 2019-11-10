---
layout: post
title: "Why do we use vectorization in Machine Learning?"
date: 2019-11-10 12:38:00 -0700
comments: true
tags: technical
---

When we do machine learning, a lot of time, we use vectors to perform any computation. The same thing can be done using the traditional method of loops too. Let's see how.

We will write a small code to take the dot problem of two numbers. For the vectorized method, we'll use numpy library and for non-vectorized method, we'll use the traditional for loop.

# Vectorized Method:

```
import numpy as np
import time

#We'll create an array of the size 100000 and populate it with random samples from a uniform distribution over [0, 1).
#For this purpose, we'l use np.random.rand()
#Link: https://docs.scipy.org/doc/numpy-1.14.0/reference/generated/numpy.random.rand.html
a =  np.random.rand(100000)
b =  np.random.rand(100000)

#We'll compute the time taken to compute the vector dot product
tic = time.time()
c = np.dot(a,b)
toc = time.time()

print(c)
print("Vectorized version:" + str(1000*(toc-tic)) + "ms")
```

# Non-Vectorized Method:

```
## Non-Vectorized Version

c = 0; tic = 0; toc = 0

#We'll compute the time taken to compute the dot product using for loop
tic = time.time()
for i in range(100000):
    c += a[i]*b[i]
toc = time.time()

print(c)
print("Vectorized version:" + str(1000*(toc-tic)) + "ms")
```


