# Knitsmart
Cilans Knitsmart Internship Project

# Confidential Data 
# Problem Statement
We want to detect anomalies on a piece of fabric, while it is manufacturing. These anomalies can occur at any time at any position on the fabric. If not caught at an early stage, it results in wastage. We want to make a robust solution, initially by using Computer Vision Techniques, and then later introduce ML if needed. The goal would be to minimise wastage while manufacturing certain kinds of cloth.

# Phase 1 : Data Collection and Computer Vision
In this phase, we’ve gathered data from the factory of the fault-less fabric as well as the different types of errors which are generated. We’ve selected two devices for the deployment of the final product. As well as two cameras for each. The specifications and camera links are mentioned below.
-	Jetson Nano (4GB Developer kit) Camera : Arducam IMX219 (B0193)
-	Raspberry PI 4 (4GB) Camera : Raspberry PI Camera

In this phase, we used automated bash scripting integrated with the respective cameras for both Jetson Nano and Raspberry PI for recording pictures as well as images. The main aim for this data collection was to use it for AI/ML/DL approach in the future. 
Moreover, we have implemented Computer Vision algorithms, in order to detect faults in the fabric. The following are the characteristics of CV :
-	Successful in detecting major faults
-	Successful in detecting needle line(minor) defects for specific settings.
-	6 algorithms are used
-	User can select any one of the 6 algorithms
-	Two phases are used:
		- Calibration
		- Inference
Calibration:
In this phase, we let the user select any one algorithm and for a predetermined time period(a few minutes), we let the algorithm train on the fabric and calculate the threshold value for it.

Inference:
Using the same algorithm on which we’ve performed calibration, we use it to do inference. In this phase, based on the threshold value obtained in the calibration phase, we process the images, and if the value for any image goes beyond threshold, fault is detected.

Moreover, based on the same underlying algorithm, we’ve created a FastAPI app, which we can deploy and use to check the efficiency of the algorithm. 
Moreover, a basic Streamlit UI has also been developed to test the recorded videos.

Here is the data collected at various phases 

Here are some pictures and videos of the implementation (that detect larger faults)

# Phase 2 : Deep Learning Approach
In this phase, we’ll be using deep learning models for effectively finding errors, especially the miniscule errors which might not be very easily detected. 
Our problem falls under the category of binary image classification problem, as there are only 2 classes for the time being, faulty and faultless images. For such problems, Convolutional Neural Networks (CNN) are best suited. 
Since we'll be using either Jetson Nano, or Raspberry PI, we need to be mindful of the computational power the model requires.
We can start with the following lightweight models:

1.	Feature Extraction + SVM

2.	Mobilenet-v2

3.	Resnet - 18 and 52

4.	Alex
5.	Xception



Topics for Research / Exploration 

1)	How to detect minor defects 
2)	Ideal setup  (distance of camera from fabric,  lighting conditions)
3)	Camera selection 
a)	Configurable FOV (to avoid unnecessary noise )
b)	Resolution  (720p, 1080p, 2K, 4K etc)
c)	FPS / frame per sec (generally 15 or 30 fps )
4)	Should we do mix …
5)	Model selection that works well for larger/small defects, accommodate different color of fabric (may be black /orange threads)  and also density of fabric (more number of threads per inch etc)


