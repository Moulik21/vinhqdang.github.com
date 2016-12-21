---
layout: post
title: "Running FastAI deep learning environment locally on Mac OS"
description: ""
category: 
tags: []
---
{% include JB/setup %}

[Fast.ai](http://course.fast.ai/) is providing a course on deep learning.

The team already set up a image which (claimed) as ready-to-use on Amazon EC2, but if you don't have enough credit, you can set up a same environment on Mac OS.

- Install [Anaconda Python](anaconda.org)
- Create a new environment

```{bash}
conda create --name fastai python
```
- Switch to the new environment


```{bash}
source activate fastai
```

- Install [theano](http://deeplearning.net/software/theano/) and [keras](https://keras.io/)

```{bash}
pip install Theano
pip install keras
```

- Install [skicit-learn](http://scikit-learn.org/)

```{bash}
conda install numpy scipy scikit-learn -y
```

- Install [opencv3](https://rivercitylabs.org/up-and-running-with-opencv3-and-python-3-anaconda-edition/)

```{bash}
conda install -c https://conda.binstar.org/menpo opencv3
```

- Install [jupyter](http://jupyter.org/)

```{bash}
pip install jupyter
```

- To run [course's notebooks](https://github.com/fastai/courses)

```{bash}
jupyter notebook
```