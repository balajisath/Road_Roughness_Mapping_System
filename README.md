# Road Roughness Mapping System

This is our senior design project completed over two semesters of an academic year. The code and information in this repository represents the work done in the machine/deep learning team of the project.

## Project Overview

Many roads in Boston are littered with potholes, remnants of poor repair work, and generally rough surfaces. As a result, vehicle drivers are burdened with huge damage costs and the suspension/bumper of vehicles face significant damages. Vehicle drivers and pedestrians are injured and fatal accidents occur in some cases as well. This calls for a smart system which would grade road roughness and provide the relevant pothole information to the user. The final deliverable will be a system that comprises an application, sensors, machine learning code, and a cloud service which work together to give the user a safe driving experience.

The user mounts his smartphone on the vehicle’s dashboard. The application on the phone collects pothole data (location, accelerometer data, and images) using the smartphone’s accelerometer, GPS, and camera. The information is uploaded to Google Firebase for storage and processing. Multiple machine learning models are trained on the collected images for predicting the roughness or severity of the potholes. A simple machine learning model is also trained on the accelerometer data to supplement the results from the neural networks. The pothole location and severity are displayed on the application using Google Maps API. The user will be able to explore the map and locate potholes easily.

## Machine Learning Component

I implemented an Inception V3 image classification model using Google Colab notebook, python, Tensorflow library, and Keras API. The model was trained on a pothole dataset. The neural net predicts whether an image is a pothole image or not. The other member on the deep learning team (Aymane) implemented and trained an image segmentation model on a pothole dataset.

We have been focusing mostly on computer vision and deep learning models. Our system collects accelerometer data which will be helpful for detecting potholes. The accelerometer data would remain stable when the vehicle is traveling on a smooth road. We would be able to see a spike on the data when the vehicle goes over a pothole. We have to leverage this to adopt and execute a model. We trained a simple machine learning model to observe anomalies in the accelerometer data. In other words, we are using a simple ML model to separate the anomaly points from the regular accelerometer data points visualized in a four dimensional space (3 dimensions for the accelerometer data and 1 dimension for the value of roughness). 

## Trained Models

- Inception V3 Image Classification Model
- Z Peak Model with Iterative Selection Threshold Method for Accelerometer Data Points

## Setup

There are two main python notebooks that implement the models. Both the notebooks are uploaded to the repository linked above. 

Senior_Design_Model1_Accelerometer.ipynb implements the Z Peak algorithm trained on the accelerometer data points. We used Python 3.10.7 for executing the notebook. You would need to have the correct version of Python to run the notebook. The required libraries and modules are mentioned in the python notebooks. You can install packages for python using the pip command if needed.

Senior_Design_InceptionV3.ipynb contains the code for training the Inception V3 neural network. Similarly, you would need to have the correct version of Python installed to execute the code. Use pip to install pacakages and modules required by the notebook. The list of necessary libraries is provided in the notebook. You would also need extended computational capacity (CPUs, GPUs) to train the neural network. Make sure the server or instance running the code has the required memory size and computational capabilities. 

The collected data is stored to Firebase and is automatically downloaded by the notebooks.
