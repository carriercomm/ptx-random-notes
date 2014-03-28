Bundler
===

purpose
---

match scale invariant features for each two-view relation

first filter the ideal data set for recovering

then obtain camera parameters and sparse point cloud

camera parameters includes 

 - translation
 - rotation
 - focal
 - 2 radial distortion

process
---

####**Phase #1 -- match features**

for each image pair

 - match features using ANN kd-tree
 - estimate fundamental matrix for the pair using RANSAC
   - each RANSAC iteration calculate candidate fundamental matrix using 8-point-algorithm
 - Levenberg-Marquardt algorithm to bundle adjustment the F-matrix and matched points (9 parameters)

essential/fundamental matrix -> 


####**Phase #2 -- generate ideal dataset**



####**Phase #3 Structure from Motion**

recover camera parameters
recover the 3D location of each track



concepts
---

####**ANN kd-tree**

spacial partition data-structure
every leaf is about same distance to the root

####**Track**

represents a 3D point
contain a set of image-feature-pair that matches each other
inconsistency is removed.(features matches each other within a image)

####**8-point-algorithm**

####**Sparse Bundle Adjustment**


---

references

[Bundler Documentation]()


