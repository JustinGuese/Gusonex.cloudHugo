+++
author = "Justin Güse"
date = 2020-02-27T21:00:00Z
description = "MTCNN is a library used to extract faces from pictures and video files using python. In this post we will take a look at how to use it, improve it, and speed it up."
draft = true
image = "/images/result.jpg"
tags = ["face detection", "face extraction", "python", "deeplearning"]
title = "Face Detection using MTCNN - a guide for face extraction with a focus on speed"
type = "post"

+++
# What is MTCNN?

MTCNN is a python (pip) library written by Github user ipacz [https://github.com/ipazc/mtcnn#zhang2016](https://github.com/ipazc/mtcnn#zhang2016 "Source"), which implements the paper Zhang, Kaipeng et al. “Joint Face Detection and Alignment Using Multitask Cascaded Convolutional Networks.” IEEE Signal Processing Letters 23.10 (2016): 1499–1503. Crossref. Web. (Link)\[[https://arxiv.org/abs/1604.02878](https://arxiv.org/abs/1604.02878 "https://arxiv.org/abs/1604.02878")\] .

In this paper they propose a deep cascaded multi-task framework using different features of "sub-models" to each boost their correlating strengths.

MTCNN performs quite fast on a CPU, even though S3FD is still quicker running on a GPU - but that is a topic for another post.

# Installation of MTCNN

Luckily MTCNN is available as a pip package, meaning we can easily install it using

    pip install mtcnn

Now switching to Python/Jupyter Notebook we can check the installation with an import and quick verification:

    # confirm mtcnn was installed correctly
    import mtcnn
    # print version
    print(mtcnn.__version__)

Afterwards we are ready to load out test image using the \[matplot\]([https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imread.html](https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imread.html "https://matplotlib.org/3.1.1/api/_as_gen/matplotlib.pyplot.imread.html"))