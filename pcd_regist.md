<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"> </script>

# 3D Vision
# Background
# Feature network
+ PointNet
  + Universal Continuous Set Function Approximator
  + Given an unorderd point set $\{x_1,x_2,..,x_n\}$ \in 
+ PointNet++
  + Extension of PointNet
# 3D Point Cloud Registration
+ Introduction
  + Definition 
    + Task aligning two or more different point clouds collected by LiDAR(Light Detection and Ranging) scanners by estimating the relative ranformation between them.
  + Challeges
    + Local sparsity
    + Large amount of data
    + noice caused by dynamic objects
  + Traditional pipeline
    + keypoint detection
    + feature descriptor extraction
    + feature matching 
    + outlier rejection
    +  transformation estimation    
+ ICP (Iterarive Closet Point)
  + Naive
  + Efficient
+ Deep based ICP
  + Overview
    + PointNet++: extract sematic features
    + corresponding point generation method using mini-PointNet
    + L1 Euclidean distance + adaptively keypoint weights and svd     