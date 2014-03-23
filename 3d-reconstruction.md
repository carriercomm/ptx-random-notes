3D Reconstruction from Image Sequence
===

Process
---

generate SIFT of images
construct initial structure from a two-view relation
add more views to the original structure
yield camera position/orientation and sparse point mesh


Intermediate Informations
---
SIFT of single image
camera positions
sparse point mesh of feature points
dense point mesh
surface


Relations and Constrains
---

`SIFT match cross two-view` --> form two view relation
`SIFT match cross multiple views` --> refine and adjust existing camera position and SIFT position
`two-view relation` (multiple two-view SIFT matches) -->  camera position/orientation and SIFT positions

Methodologies
---

`MVS (Multi-View Stereo)`
`SfM`



Existing Tools
---

`Bundler`

 - **main objective -- produce camera positions from images**
 - input -- images, image features, image matches
 - output -- camera position and parse point clouds
 - incremental, a few images at a time, 
 - use Sparse Bundle Adjustment as underlying optimization engine


`SBA (Sparse Bundle Adjustment)`

 -  **main objective -- use redundant feature matches to refine camera positions**


`PMVS2 (Patch based MVS version 2)`

 - **main objective -- produce dense oriented point cloud using images and their camera information**
 - input -- images, camera positions, 
 - produce dense point cloud, points are oriented, with estimated surface normal

`CMVS (Clustering view for MVS)`

 - **main objective -- divide and conquer**
 - input -- out put of SfM
 - use in conjunction with Bundler(SfM) and PMVS2(MVS)
 - decompose input images into a set of clusters (if managable size)
 - use another MVS program to process the clusters in parallel


Workflow
---

SIFT --> Bundler(SBA) --> CMVS --> PMVS2


File Formats
---

**SIFT**
input: images
output: images + feature list


**match feature**
input: images + feature list
output: features with list of occurence

**bundler**

input: 

output:

 - .ply sparse point cloud
 - camera information
    - translation (3 vector)
    - rotation (3*3 matrix)
    - focal and 2 * radial distortion
 - points
    - position (3-vector)
    - color (3-vector)
    - view list

**PMVS2**




