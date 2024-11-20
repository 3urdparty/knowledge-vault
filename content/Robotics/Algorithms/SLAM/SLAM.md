![[Pasted image 20241104122154.png]]

Mapping with certainty
![[Pasted image 20241104122940.png]]
Mapping with uncertainty
![[Pasted image 20241104122922.png]]
Nearing the end of a scan, youll reach a point that has been seen before. the algorithm has to detect that it has been seen before and "loop-close"
![[Pasted image 20241104123548.png]]


# Overview
## Pipeline
1. [[#Feature Extraction]] - Identifying key features
2. [[#Feature Matching]] - matching identified features between current frame and previous frame
3. [[#Motion Estimation]] - Estimating camera's motion based on feature matching step
4. [[#Data Association]] - matching features to existing map elements or identifying new elements to be added to map
5. [[#Map Management]] - update map, handling addition of new maps and removing obsolete ones
6. [[#Pose Graph Estimation]] - local and global optimizations to refine the estimated poses and map, reducing the accumulated errors
7. [[#Localization]]
8. [[#Mapping]]
9. [[#Loop Closing]]

### Feature Extraction
Stage at which we to identify distinctive key features to focus on in the next stage, [[#Feature Matching]] to discern the motion. 
![[feature-extraction]]
Involves identifying distinctive parts of an image, such as edges, corners, shapes, textures, or patterns, to help with the localization and mapping process. 
You can run ORB feature extraction via [[opencv]]:

```python
import numpy as np
import cv2 as cv
from matplotlib import pyplot as plt
 
img = cv.imread('./assets/test.jpeg', cv.IMREAD_GRAYSCALE)
 
# Initiate ORB detector
orb = cv.ORB_create()
 
# find the keypoints with ORB
kp = orb.detect(img,None)
 
# compute the descriptors with ORB
kp, des = orb.compute(img, kp)
 
# draw only keypoints location,not size and orientation
img2 = cv.drawKeypoints(img, kp, None, color=(0,255,0), flags=0)
plt.imshow(img2), plt.show()
```
![[Pasted image 20241107150821.png|300]]
![[Pasted image 20241107150927.png|400]]
![[Pasted image 20241107150937.png|500]]
![[Pasted image 20241107151419.png]]
With Size and Orientation
![[Pasted image 20241107151107.png]]
![[Pasted image 20241107175006.png]]
#### Algorithms
##### ORB
Efficient, robust, and rotation invariant. uses a combination of **FAST** keypoint detection and **BRIEF** binary descriptor

FAST (Features from Accelerated Segment Test): corner detection algorithm designed for high-speed feature detection.
1. examine 16 pixels in a circle around a candidate point
2. A pixel is classified as a corner if there exists a set of continuous pixels in the circle that are all brighter or all darker than the center pixel by some threshold

- Uses a simple pixel intensity comparison test
- Employs a quick rejection strategy for non-corners
- Can terminate the test early once sufficient evidence is found

BRIEF (Binary Robust Independent Elementary Features): Creates a binary string to describe a detected feature

1. Selecting pairs of pixels in the feature's neighborhood
2. Comparing their intensities
3. Assigning 0 or 1 based on which pixel is brighter

- Very fast to compute (just pixel comparisons)
- Efficient to store (binary string)
- Fast to match (using Hamming distance)
- Good recognition performance despite simplicity

SIFT (Scale Invariant Feature Transform):

Invariant to:
- Scale changes
- Rotation
- Translation
- Partial illumination change
- Affine distortion
- Noise

1. Scale-space Extrema Detection:
	1. Creates a scale space by convolving the image with Gaussian filters at different scales
	2. Computes Difference of Gaussians (DoG) between adjacent scales
	3. Locates potential keypoints by finding local extrema in DoG images
2. Keypoint Localization:
	1. Refines keypoint locations using interpolation
	2. Rejects low-contrast points and edges
	3. Ensures stability of detected points
3. Orientation Assignment:
	1. Computes gradient magnitude and direction around each keypoint
	2. Creates histogram of local gradient directions
	3. Assigns one or more orientations based on peak directions
	4. This step provides rotation invariance
4. Keypoint Descriptor Generation:
	1. Takes 16x16 neighborhood around keypoint
	2. Divides into 4x4 subregions
	3. Creates 8-bin orientation histogram for each subregion
	4. Results in 128-dimensional feature vector (4x4x8)
	5. Normalizes vector for illumination invariance

The Improved SIFT algorithm can improve the accuracy and robustness of a SLAM system. 
CNN-based
CNN-based feature-point extraction methods have made progress in feature-point detection and descriptor generation. However, they can be computationally and storage complex. 
Feature extraction is a preprocessing method that transforms raw data into numerical features that can be processed while preserving the original data set. This can yield better results than applying machine learning directly to the raw data. 
SLAM is the foundation of augmented reality (AR), allowing AR devices to perceive the world in three dimensions. 


Workflow:
1. Take Video and split to frames
2. Convert frames to depth maps via:
```bash
heif-convert --with-aux ~/Downloads/test.heic ~/Downloads/test.jpg
```


### Feature Matching
### Motion Estimation
### Data Association
### Map Management
### Map Management