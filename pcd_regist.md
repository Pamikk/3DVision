<script type="text/javascript" src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=default"> </script>

# 3D Point Cloud Registration
# Feature network
+ PointNet
  + Universal Continuous Set Function Approximator
  + Given an unorderd point set $\{x_1,x_2,..,x_n\}$ \in 
+ PointNet++
  + Extension of PointNet
  + Hierarchical Point Set Feature Learning
  + Structure
    + N x (d+C) -> N'x(d+C')
    + Sampling layer
      + Iterative fartherst point sampling(FPS)
      + better coverage the entire point set give nthe same number of controids
    + Grouping Layer
    +    

# Methods
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
  + Structure
    + Feature Extraction  
      + N1x4 -> N1x32
      + PointNet++
    + Point Weighting
      + learn the saliency of each point 
      + MLP of 3 stacking fully connected layers and topk operation
      + BN and ReLU for first two, softplus activation func for last
      + find the top N
    + Deep Feature Embedding
      + find N corresponding points in the target point cloud
      + Specifically, collect K neighboring points within a certain radius d of each keypoint.
      + mini-PointNet
      + input: NxKx36(with cat)
    + Corresponding Point Generation
    + SVD to calculate the relative transformation       