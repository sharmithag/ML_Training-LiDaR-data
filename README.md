# ML_Training-LiDAR-data 

## Problem Statement

![image](https://user-images.githubusercontent.com/90351952/190183649-1589d1c4-8b49-4e13-ba3b-01d38e2d6331.png)

## Approach

Data collected from a car like robot (mobile robot) with LiDAR driven in open and corridor environments is trained and tested to predict future action commands i.e translational velocity (v) and rotational velocity(w). The data is trained using LINEAR REGRESSION and also using NEURAL NETWORKS for a performance comparison.  

## Datasets

Training  Data with instructions on format of data (see readme file) are available at 
https://drive.google.com/drive/folders/1IgiPMaMyktjIa9qH-5qqSjwFuew9TiPW?usp=sharing
Test data is available at https://drive.google.com/drive/folders/1IhVbX1VwAQf4WzamN8m81sNQTABDWw5y?usp=sharing

The laser range data and the positional data are given in the dataset.

## Data pre-processing

### How to view the unprocessed data?
The laser range data from the LIDAR is a 1D array of 1080 values which is the range recorded at each 0.25deg within a 270deg field of view with the 540th element being the range corresponding to directly in front of the robot.
The robot current position, the local and final goal information are given in 3D cartesian coordinates (x; y; z) for position and a quaternion (q = qr + qi*i + qj*j + qk*k) for the orientation. Here, only the horizontal plane is considered, i.e, x and y and qr and qk in quaternion. 

### Processing overview
For laser data, a field of view of 30 degrees is considered  as one value and hence the laser data is brought down to 9 columns. 
For the positional data, the quaternion sum q is taken adding qr and qk. Hence, the current robot position, the local goal and the final goal positional data has x, y and q values contributing 3 columns each. The input features have been brought down from 1080 to 18 columns.
