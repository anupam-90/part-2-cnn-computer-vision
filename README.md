## Part 1: Problem Identification
DATASET:https://drive.google.com/drive/folders/17xoSIAe-24-18iJiN3zKPqJl-RNDqIeW?usp=drive_link

**Problem Type:** Image Classification

**Why this is appropriate:** The dataset provides product images and associates each of them with a single categorical label which are nornal, scratch, dent, and stain. There are no bounding box annotations which are required for object detection nor there are are pixel wise masks which would be required for Segmentation. The goal here is to simply assign the correct categorical label to a given image based on its overall contents, making this a standard multiclass image classification task. 

## Part 6 CNN Concept Explanation
**What is convolution?**
A grid of numbers which are called filters or kernel slides across the image pixels, at each step the model does simple maths to detect visual features like vertical edges, lines, corners or eventually complex shapes, in its way it is scanning the image for patterns. 

**Why is pooling used?**
Pooling means creating an executive summary for the network, after each convolution layer finds various features, the image representation beomes heavy mathematically. Pooling looks at small patches of the image and keeps only the most prominent feature while discarding the rest. This helps the model in two ways, one by drastically shrinking the size of data, it increases the effeciency of the model and requires less memory to process. Second, It helps the model to recognize objects which might be slightly off centered, rotated or shifted since the exact pixel location becomes less rigid. 

**Why ReLu is commonly used in CNNs?**
It stands for Rectified Linear Unit, if a number is negative, it changes it to 0(zero) or if the its positive it doesnt change the number. The main reasons to use ReLu is that it makes the math incredibly fast, which is almost necessary when processing millions of pixels. Secondly, it also stops the 'vanishing gradient' which the older models like Sigmoid would cause learning signals to shrink to zero as they passed through deep networks, which in turn would mean that the network will stop learning. ReLu helps prevent this and allows deep networks to learn effectively. 

**Why are CNNs better than regular feed-forward networks for image data?**
When using feed-forward network, we must 'flatten' the image first, which means a 100 by 100 image would be straightened into a straight line of 10,000 pixels which would destray the spatial relationship between the pixels. Meaning that if pixel A and pixel B are right next to each other, this context is lost in regular feed forward networks hence making it hard for to recognize if a circle is an eye or a wheel. On the other hand, CNNs, look at the image in its orignal 2D shape, they take into account the local neighbourhoods of pixels, allowing them to grasp the spatial structure, objects, and textures, which makes them far superior for computer vision. 

## Task 7: Business Use Case: Autonomous Vehicles & Fleet Management 
When autonomous vehicle returns to a depot or rental car is dropped off by a customer, it must be rigourously inspected for wear, tear, and passenger damage before it can be safely dispatched to the next user. A computer vision system powered by CNN can automate this entire inspection pipeline. This model can be used in many ways like:

    1. Exterior Damage Assessment: As the vehicles drives through an automated scanning bay where cameras captures the images for each panels and wheel. CNN then instantly evaluates the images, distinguishing a normal panel from a scratch or a dent.

    2. Interior Cabin Monitoring: Customer submitted pictures of the cabin as a part of post rental check, it will help scan the floor mats and seats for things like a stain or scratch on the leathy upholstery, alerting the system that car is ready for the next rider. 
    
    3. Business impact: Deploying this model completely removes the need for manual labour after each rental ends. Fleet operators to instantly route damaged and dirty vehicles to repair shops, deploy cleaning crews exaclty when and where they are needed, and automatically bill the previous passenger for specific damages, this drastically reduces operational bottlenecks and improves vehicle turnaround time. 