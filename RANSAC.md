**RANSAC** (Random Sample Consensus)
===

###purpose
In a set of samples containing `inlier`(valid) and `outlier`(noise),  RANSAC attempts to select a inlier-only sample set by random selection within a finite number of trials.

###assertions

**sample set is inlier only**:  if the percentage of samples that tolerate this estimate model is above threshold

**chance of succeed**: `1-(1-threshold^n)^trials`


###example

two images have a set of feature matches, some of the matches are valid, some of them are noise

we need to reject the outliers so that `8-point-algorithm` and `bundle adjustment` can be applied to estimate camera parameters


###components

 - `model` -- the fundamental matrix
 - `model generator` -- 8-point-algorithm -- take 8 point matches to generate a fundamental matrix
 - `sample` -- 3D point and their projections on two cameras


###process

 - randomly choose minimum number of samples required for constructing a model
 - use `model generator` to generate an estimated model use this sample set
 - calculate percentage of samples which tolerate this estimate model
   - if below threshold, start over, until out of quota
   - if above threshold
     - discard samples that don't tolerate (outliers)
     - accept consensus samples (inlier) 
     - refine the estimated model using consensus samples
 

###parameters:

 - `tolerance` -- tolerated error
 - `threshold` -- estimated inlier percentage
 - `N`-- quota of trials

---

####references

[Wikipedia:RANSAC](http://en.wikipedia.org/wiki/RANSAC)

[Overview of RANSAC Algorithm](http://www.cse.yorku.ca/~kosta/CompVis_Notes/ransac.pdf)