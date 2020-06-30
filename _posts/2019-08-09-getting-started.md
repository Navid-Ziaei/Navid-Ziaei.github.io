---
title: TensorFlow2
author: Navid Ziaei
date: 2020-07-01 20:55:00 +0800
categories: [DeepLearning, Tutorial]
tags: [Deep Learning, TensorFlow, Machine Learning]
pin: true
---

## Why We Should use Tensorflow2

If you were intrested in Keras or Torch beacuse of it's simplicity to build different model, or if you were a Thiano or Tensorflow specialist who has a strong interest in post-network mathematics, It's time to megerate to Tensorflow 2! a new frame work that has combined keras simplisity with tensorflow 1 abilities.
Now it's supported by conda and you can easily install it using conda.

* Conda Installation cpu

```console
$ conda create -n tf2 python=3.6 tensorflow
```


* Conda Installation gpu

```console
$ conda create -n tf2 python=3.6 tensorflow-gpu
```

Don't forget to install CUDA Toolkit V>10 for GPU Version of tensorflow. now you don't need to install Keras as a single package. It's already installed as a bulit-in API.



# What Hase Changed?
In simple terms, TensorFlow 2 threw all the crap away and swallowed Keras. We now have all the prototyping goodness within TensorFlow. Then, the eager mode became the default, just like PyTorch. We can even define models as Python classes. Finally, this was all done without compromising TensorFlow’s edge on deployment, nor the speed of compiled code
## Simple Network Building
Keras as a built-in API, Enable Tensorflow 2 to create network using predefined layers.

## No more session
One of the most confusing parts of tensorflow1 was sessions. now sessions has removed from tensorflow.

## What about custom layers?
I don't want predefined layers! I NEED my own layes!
No problem. That's OK! you can build every layer you want using Tensorflow power!

## Training
You can easily fit a model with keras methods and you can also build your loss and create your special training scheme using custum loops and calculating gradient


## A suggestion to keras users

If you are a keras user, don't be afraid! nothing will change for you. migerate to tensorflow. keras as a seperate package will not support. migerate and use the power of tensorflow along with keras methods and objects.



# Simple Comparison between Tensorflow 1 and 2
##Ease of use
Many old libraries (example tf.contrib) were removed, and some consolidated. For example, in TensorFlow1.x the model could be made using Contrib, layers, Keras or estimators, so many options for the same task confused many new users. TensorFlow 2.0 promotes TensorFlow Keras for model experimentation and Estimators for scaled serving, and the two APIs are very convenient to use.

##Eager Execution
In TensorFlow 1.x. The writing of code was divided into two parts: building the computational graph and later creating a session to execute it. this was quite cumbersome, especially if in the big model that you have designed, a small error existed somewhere in the beginning. TensorFlow2.0 Eager Execution is implemented by default, i.e. you no longer need to create a session to run the computational graph,  you can see the result of your code directly without the need of creating Session.


##Model Building and deploying made easy
With TensorFlow2.0 providing high level TensorFlow Keras API, the user has a greater flexibility in creating the model. One can define model using Keras functional or sequential API. The TensorFlow Estimator API allows one to run model on a local host or on a distributed multi-server environment without changing your model. Computational graphs are powerful in terms of performance, in TensorFlow 2.0 you can use the decorator tf.function so that the following function block is run as a single graph. This is done via the powerful Autograph feature of TensorFlow 2.0. This allows users to optimize the function and increase portability. And the best part you can write the function using natural Python syntax. Effectively, you can use the decorator tf.function to turn  plain Python code into graph. While the decorator @tf.function applies to the function block immediately following it, any functions called by it will be executed in graph mode as well. Thus, in TensorFlow 2.0, users should refactor their code into smaller functions which are called as needed. In general, it's not necessary to decorate each of these smaller functions with tf.function; only use tf.function to decorate high-level computations - for example, one step of training, or the forward pass of your model. (source stack overflow and TF2 documentation)

To expand this idea, In TensorFlow 1.x we needed to build the computational graph. TensorFlow 2.0 does not build graph by default. However, as every Machine Learning engineer knows, graphs are good for speed. TensorFlow 2.0 provides the user to create a callable graph using a python function @tf.function. The tf.function() will create a separate graph for every unique set of input shapes and datatypes. In the example below we will have three separate graphs created, one for each input datatype.

##The Data pipeline simplified
TensorFlow2.0 has a separate module TensorFlow DataSets that can be used to operate with the model in more elegant way. Not only it has a large range of existing datasets, making your job of experimenting with a new architecture easier - it also has well defined way to add your data to it.

 

In TensorFlow 1.x for building a model we would first need to declare placeholders. These were the dummy variables which will later (in the session) used to feed data to the model. There were many built-in APIs for building the layers like tf.contrib, tf.layers and tf.keras, one could also build layers by defining the actual mathematical operations.

TensorFlow 2.0 you can build your model defining your own mathematical operations, as before you can use math module (tf.math) and linear algebra (tf.linalg) module. However, you can take advantage of the high level Keras API and tf.layers module. The important part is we do not need to define placeholders any more.

