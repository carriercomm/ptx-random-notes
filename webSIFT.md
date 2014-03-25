WebSIFT
===

Important Concepts
---
####**Gradient**

 - use Sobel Operator

####**Sobel Operator** (derivative)

 - matrix convolution [1 2 1][-1 0 1]

####**Convolution**

 - multiply by position, then sum

####**Guassian** (blur)

 - convolution by Guassian Matrix
 - sigma is the parameter

####**Grayscale**
RGB - 0.2989, 0.5870, 0.1140

Process
---
1. generate octave-scale space
2. generate DOGs
3. find key-points in DOGs
4. filter key-points
5. assign orientation to key-points
6. assign descriptor to oriented-key-points

Parameters
---

1. key-point contrast threshold
2. guassian sigma -- sqrt(2)
3. octave-scale levels