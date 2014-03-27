Epipolar Geometry
===

purpose
---

the basic construct of epipolar geometry is `two-view relation`

complex structures can be represented by a map of two-view relations

a two-view relation consists of

 - `2 * cameras` (each has its own projection center, image plane, camera parameters)
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

the plane setup by two cameras and the point

it intersects each image plane at the epipolar line

####**Epipolar Constraint**

 - using `triangulation` to obtain the spacial point coordinate from coordinates on the image planes with camera parameters 
 - the two-view relation can be described using `essential matrix` or `fundamental matrix`
 - **Essential Matrix** (for calibrated cameras)
 - **Fundamental Matrix** (for un-calibrated cameras)

####**Homogeneous Coordinate**
`affine transformation` and `projective transformation` can be represented as matrix multiplication

####**Camera Matrix**
conversion matrix between 3D point and 2D projection point (homogeneous coordinate)


---

references

[Wikipedia:EpipolarGeometry](http://en.wikipedia.org/wiki/Epipolar_geometry)

[Wikipedia:HomogeneousCoordinates](http://en.wikipedia.org/wiki/Homogeneous_coordinates)

[Essential and Fundamental Matrices](http://vision.stanford.edu/~birch/projective/node20.html)


