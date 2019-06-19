# CompVisionDopeProject
Semester project - Computer Vision - PhD Jeleń

Topic: Object pose estimation based on camera vision using Machine Learning methods. Implementation for embedded platform.

Authors:

·         Adam Loch 218595

·         Szymon Wojciechowski 218154

Goal: Create implementation which will be able to estimate pose of sample object which is nearly-symetrical and poorly textured (STL in repo). Implementation must work on embedded platform, which will support Neural Networks calculations and image acquisition via connected camera. Learning will done on synthetic samples (CAD model renders).

References:

·         Deep Object Pose Estimation for Semantic Robotic Grasping of Household Objects, Jonathan Tremblay at. el., 2018.



# Preparation
1. CAD model has to be converted to FBX/OBJ, with textures (colors from STL files are not enough)
2. Dimensions in CAD has to be saved in meters
3. Whole object should be grouped
4. Camera has to be calibrated -> camera matrix

# Dataset synthetizing
1. Install Unreal Engine 4.21v
2. Follow tutorial on creating scene (in NDDS's docs)
    In case of nearly-symetrical, poorly textured object its recommended to use high amount of random lights + no occlusion added. 100k images has been generated using COCO's images as a background.
3. Modify camera parameters in order to replicate image distortion

# Dope training
Architecture of the network has been modified to obtain more low level features in final prediction. During training SGD gave much smoother results (Adam, sometimes instantly increased loss). 

# Dope runtime
Runtime script has not been edited in comparision to orginal DOPE's repo.

References:

Jonathan Tremblay and Thang To and Balakumar Sundaralingam and Yu Xiang and Dieter Fox and Stan Birchfield
Deep Object Pose Estimation for Semantic Robotic Grasping of Household Objects
