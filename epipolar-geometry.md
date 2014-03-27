Epipolar Geometry
===

purpose
---
the basic construct of epipolar geometry is two-view-relation

a two-view relation consists of

 - `2 * cameras` (each has its own projection center, image plane)
 - `the point` (seen by both cameras, **1* 3D spacial coordinate** and **2 * 2D image coordinates**)
 - `2 * epipolar point` 
 - `2 * epipolar line` 
 - `1 * epipolar plane`

a two-view relation forms a **epipolar constraint**
the epipolar constraint can be used in finding coordinates, verification, parameter refinement (bundle ) .etc

concepts
---

####**Epipolar Point** (epipole)
2D projection of the other camera's projection center

####**Epipolar Line**
2D projection of the other camera's projection line (projection center to the 3D point)
two endpoints are the `epipolar point` and the `projection point`

####**Epipolar Plane**
the plane setup by two camera and the spacial point
epipolar lines are the intersections with two image planes

####**Epipolar Constraint**

 - `triangulation`, obtain the spacial point coordinate from coordinates on the image planes with camera parameters 
 - the two-view relation, can be described as `essential matrix` or `fundamental matrix`, `y'Ey=0`
 - **Essential Matrix** (for calibrated cameras)
 - **Fundamental Matrix** (for un-calibrated cameras)

**Homogeneous Coordinate**
affine transformation/projective transformation can be represented as matrix product

**Camera Matrix**
`homogeneous coordinate` conversion matrix between 3D point and 2D projection point

