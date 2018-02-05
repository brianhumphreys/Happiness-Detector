# Happiness-Detector
Python program that uses cv2 libraries to implement the Viola-Jones Algorithm with a simple method that takes a color frame and a grey-scale frame as an input from a live web-cam

This repository is a first in a series of three that display my understanding of Computer Vision and how different networks create different results of detection.  In this Viola-Jones algorithm, the images are compared to a network with weights that are positioned to the location and frequency of three basic pixel features, or 'Haar-Like Features.'  

The detect function, found in face_recognition_commented.py, takes in an image and gives every pixel a number value based off the average of all the greyscale values of all the pixels to the left and up of its positions.  These initial calculations create an Integral Image that is used to calculate the patterns of pixel values that will be compared to the three Haar-like features to determine if that pattern instance is present.  This compaison technique is applied to 180,000 rectangular sections for each image.  

Once the algorithm detects a frame that contains a face, it will concentrate on just that frame to repeat the same comparison technique for the haar-like feature stucture of human eyes.  It surrounds any eye found with a green rectangle.  The happiness part of the detection is determined by training the network with pictures of smiles, frowns and neutral mouths.  

The parameters in detectMultiScale include values for minimum neighbors and flag numbers.  I find that when detecting smiles as opposed to frowns or neutral positions, the minimum number of neighbors each candidate rectangle should have to retain positive detection, should be around 2.2, while flag should be much higher around 22.
