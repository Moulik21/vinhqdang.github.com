---
layout: post
title: "GPU computing with tensorflow on Mac OS 10.12"
description: ""
category: 
tags: []
---
{% include JB/setup %}

The newest version 0.10.0rc of [tensorflow](https://www.tensorflow.org/) does support GPU computing on Mac OS. Users can follow the [instruction](https://www.tensorflow.org/versions/r0.10/get_started/os_setup.html#using-pip). Using [Anaconda environment management](http://conda.pydata.org/docs/using/envs.html) is highly recommended. Remember to install [CUDA >= 7.5](https://developer.nvidia.com/cuda-zone) and [cudnn >= 5](https://developer.nvidia.com/cudnn) before installing tensorflow.

After installation, you can check your new tensorflow as (for Python 2):

```
python -c 'import tensorflow as tf; print(tf.__version__)'
```

You might see an error:

```
I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcublas.dylib locally
I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcudnn.dylib locally
I tensorflow/stream_executor/dso_loader.cc:108] successfully opened CUDA library libcufft.dylib locally
I tensorflow/stream_executor/dso_loader.cc:102] Couldn't open CUDA library libcuda.1.dylib. LD_LIBRARY_PATH: /Users/qdang/torch/install/lib:/usr/local/cuda/lib:
...
```

Fixing it is easy. Supposed you installed CUDA at the default location (/usr/local/cuda):

```
cp /usr/local/cuda/lib/libcuda.dylib /usr/local/cuda/lib/libcuda.1.dylib
```

and tried again.