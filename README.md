# Emotion-Detection
Emotion-detection
Introduction
This project aims to classify the emotion on a person's face into one of seven categories, using deep convolutional neural networks. This repository is an implementation of this research paper. The model is trained on the FER-2013 dataset which was published on International Conference on Machine Learning (ICML). This dataset consists of 35887 grayscale, 48x48 sized face images with seven emotions - angry, disgusted, fearful, happy, neutral, sad and surprised.

Dependencies
Python 3, OpenCV 3 or 4, Tensorflow 1 or 2
To install the required packages, run pip install -r requirements.txt.
Usage
The repository is currently compatible with tensorflow-2.0 and makes use of the Keras API using the tensorflow.keras library.

First, clone the repository with git clone https://github.com/atulapra/Emotion-detection.git and enter the cloned folder: cd Emotion-detection.

Download the FER-2013 dataset from here and unzip it inside the Tensorflow folder. This will create the folder data.

If you want to train this model or train after making changes to the model, use python emotions.py --mode train.

If you want to view the predictions without training again, you can download my pre-trained model (model.h5) from here and then run python emotions.py --mode display.

The folder structure is of the form:
Tensorflow:

data (folder)
emotions.py (file)
haarcascade_frontalface_default.xml (file)
model.h5 (file)
This implementation by default detects emotions on all faces in the webcam feed.

With a simple 4-layer CNN, the test accuracy peaked at around 50 epochs at an accuracy of 63.2%.

![image](https://github.com/user-attachments/assets/345297c0-ef46-4b3e-ad75-9deee96f9d22)

Accuracy plot

Algorithm
First, we use haar cascade to detect faces in each frame of the webcam feed.

The region of image containing the face is resized to 48x48 and is passed as input to the ConvNet.

The network outputs a list of softmax scores for the seven classes.

The emotion with maximum score is displayed on the screen.
