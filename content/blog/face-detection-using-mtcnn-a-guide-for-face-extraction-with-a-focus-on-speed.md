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

# Basic usage of MTCNN

Luckily MTCNN is available as a pip package, meaning we can easily install it using

    pip install mtcnn

Now switching to Python/Jupyter Notebook we can check the installation with an import and quick verification:

    import mtcnn
    # print version
    print(mtcnn.__version__)

Afterwards, we are ready to load out test image using the matplotlib imread function [https://bit.ly/2vo3INw](https://bit.ly/2vo3INw "https://bit.ly/2vo3INw").

    import matplotlib.pyplot as plt
    # load image from file
    filename = "glediston-bastos-ZtmmR9D_2tA-unsplash.jpg"
    pixels = plt.imread(filename)
    print("Shape of image/array:",pixels.shape)
    imgplot = plt.imshow(pixels)
    plt.show()

Now your output will look a lot like this:

    {'box': [1942, 716, 334, 415], 'confidence': 0.9999997615814209, 'keypoints': {'left_eye': (2053, 901), 'right_eye': (2205, 897), 'nose': (2139, 976), 'mouth_left': (2058, 1029), 'mouth_right': (2206, 1023)}}
    {'box': [2084, 396, 37, 46], 'confidence': 0.9999206066131592, 'keypoints': {'left_eye': (2094, 414), 'right_eye': (2112, 414), 'nose': (2102, 426), 'mouth_left': (2095, 432), 'mouth_right': (2112, 431)}}
    {'box': [1980, 381, 44, 59], 'confidence': 0.9998701810836792, 'keypoints': {'left_eye': (1997, 404), 'right_eye': (2019, 407), 'nose': (2010, 417), 'mouth_left': (1995, 425), 'mouth_right': (2015, 427)}}
    {'box': [2039, 395, 39, 46], 'confidence': 0.9993435740470886, 'keypoints': {'left_eye': (2054, 409), 'right_eye': (2071, 415), 'nose': (2058, 422), 'mouth_left': (2048, 425), 'mouth_right': (2065, 431)}}

What does this tell us? A lot of it is self-explanatory, but it basically returns coordinates, or the pixel values of a rectangle where the MTCNN algorithm detected faces. The "box" value above returns the location of the whole face, followed by a "confidence" level.

If you want to do more advanced extractions or algorithms, you will have access to other facial landmarks, called "keypoints" as well. Namely the MTCNN model located the eyes, mouth and nose as well!

To demonstrate this even better let us draw a box around the face using matplotlib:

    # draw an image with detected objects
    def draw_facebox(filename, result_list):
        # load the image
        data = plt.imread(filename)
        # plot the image
        plt.imshow(data)
        # get the context for drawing boxes
        ax = plt.gca()
        # plot each box
        for result in result_list:
            # get coordinates
            x, y, width, height = result['box']
            # create the shape
            rect = plt.Rectangle((x, y), width, height, fill=False, color='green')
            # draw the box
            ax.add_patch(rect)
        # show the plot
        plt.show()
     
    # filename = 'test1.jpg' # filename is defined above, otherwise uncomment
    # load image from file
    # pixels = plt.imread(filename) # defined above, otherwise uncomment
    # detector is defined above, otherwise uncomment
    #detector = mtcnn.MTCNN()
    # detect faces in the image
    faces = detector.detect_faces(pixels)
    # display faces on the original image
    draw_facebox(filename, faces)

![MTCNN detected box around face](/images/index.png "MTCNN detected box around face")