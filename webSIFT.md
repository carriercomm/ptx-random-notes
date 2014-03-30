WebSIFT
===

purpose
---


process
---
1. generate octave-scale space
2. generate DOGs
3. find key-points in DOGs
4. filter key-points
5. assign orientation to key-points
6. assign descriptor to oriented-key-points

parameters
---

1. key-point contrast threshold
2. guassian sigma -- sqrt(2)
3. octave-scale levels


implementation details
---

####**Gradient**

 - use Sobel Operator

####**Guassian** (blur)

 - convolution by Guassian Matrix
 - sigma is the parameter

####**Guass Blur**

parameter : sigma(diameter)

####**Sobel Operator** (derivative)

 - use sobel operator to calculate the gradient at a point
 - convolute the sobel matrix
 - matrix convolution [1 2 1][-1 0 1]


####**Grayscale**
RGB - 0.2989, 0.5870, 0.1140

####**Convolution**

 - multiply by position, then sum


---

references

[Wikipedia: Sobel Operator](http://en.wikipedia.org/wiki/Sobel_operator)

[Sobel Edge Detector](http://homepages.inf.ed.ac.uk/rbf/HIPR2/sobel.htm)