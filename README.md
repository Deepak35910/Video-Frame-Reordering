# Video-Frame-Reordering

In this project we will try to regenerate original video whose frames have been reshuffle. We will first read a video in its original form and then randomly shuffle frames and then using Machine Learning and Statistics will try to reorder frames to regenerate original video. We can do pixel to pixel comparison to group frames which are similar to each other by calculating distance between corresponding pixels but it has 2 limitations. we can get distance between frames but we don't know how to arrange them, and secondly if camera moves pixel corresponding to particular object will be in different positions and we will get larger distance between two frames which are similar to each other but taken at a slightly different angle. Instead of comparing pixels we can compare features of an image.

INCEPTION

Model likes Inception are trained on huge data to classify images. They do so by various convolution layers and then fully connected layers in the later part. We can use these later fully connected layers which contains information of different feature. The final fully connected layers is an array of numbers of length 2048. These 2048 numbers are not interpretable but we can assume each of these numbers conveys some information of a feature. For instance, one of the number may correspond to how much of chance of having a human in a given image and other number may correspond to how much of a chance of a given image having a car. So we can assume 1st value of this array is for human and high value means there are higher chance of having a person in this image and low value will correspond to a lower chance. Similarly 2nd value can be assumed to be of a car and so on. So instead of comparing pixels we will compare feature vector where compared value won’t be affected by much if camera angle changes as the features value of an image like human, car remain the same if the camera angle are slightly different for different frames. Meaning if there is a car in the image taken from slightly different angle our feature vector will still detect car with almost equal probability and thus the value corresponding to a car in the feature vector will still be similar and so would be distance between frames

TSNE

TSNE takes data of m dimension and reduces the dimesion to as low as 1. It reduces dimesion based on similarity. Data which are closer to each other in m dimesion are more similar to each other and are grouped together in lower dimesion. It gives similar values to Data which are closer to each other and values changes as data gets farther from each other. We can use this concept to arrange frames which are in 2048 dimesion after passing from Inception layer to reduce them to 1 dimesion We can then arrange this data as per TSNE values and hopefully we will be able to get proper sequence.

FILES
reorder_video_frame.ipynb - all the codes (was written in colab)
Play_video.ipynb - to play all video 

Link for video file
https://drive.google.com/drive/folders/1muuj3Qt3w9Mc48Kt7zzYtEBgW5c1elFd?usp=sharing

