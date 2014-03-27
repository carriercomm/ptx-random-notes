WebBundler
===

Process
---
for each image pair

 - match features using ANN kd-tree
 - estimate fundamental matrix for the pair using RANSAC
   - each RANSCA iteration calculate candidate fundamental matrix using 8-point-algorithm
 - Levenberg-Marquardt algorithm to bundle adjustment the F-matrix and matched points (9 parameters)

Concepts
---

ANN kd-tree
every leaf is about same distance to the root

Levenberg-Marquardt algorithm


8-point-algorithm

sparse bundle adjustment

Data
---

**Camera Parameters**

 - focal
 - 2 * radial distortion




