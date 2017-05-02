---
title: 在 mac 上通过 virtualenv 安装 tensorflow
date: 2017-05-01 10:47:49
tags: tensorflow
---
```
sudo easy_install pip
```
```
sudo pip install --upgrade virtualenv
```
```
virtualenv --system-site-packages ~/development\ projects/tensorflow
```
```
source ~/development\ projects/tensorflow/bin/activate  # If using bash
```
```
# Mac OS X, CPU only, Python 2.7:
(tensorflow)$ export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-0.12.0rc1-py2-none-any.whl

# Mac OS X, GPU enabled, Python 2.7:
(tensorflow)$ export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-0.12.0rc1-py2-none-any.whl

# Mac OS X, CPU only, Python 3.4 or 3.5:
(tensorflow)$ export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/cpu/tensorflow-0.12.0rc1-py3-none-any.whl

# Mac OS X, GPU enabled, Python 3.4 or 3.5:
(tensorflow)$ export TF_BINARY_URL=https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-0.12.0rc1-py3-none-any.whl
```
```
pip install --upgrade $TF_BINARY_URL
```