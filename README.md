# Image_Stiching
 Stitch together a single pair of images using homography mapping
 
 <p> To run the code for image stiching, run <b> stiching.ipynb </b> <br> The input images and intermediate results are in <b> givenImage </b> folder. </p>
 
 <h3> Description of code </h3>
 <p> 

<ul>
 <li>  Consider a pair of images which are to be stitched together
<img src="url"> </li>
 <li>Compute the sift-keypoints and descriptors for both the images using  cv2.xfeatures2d.SIFT_create().detectAndCompute()
  </li>
 <li>
   The distances between every descriptor in one image and every descriptor in the  other image are computed.</li><li> All pairs whose descriptor distances are below a specified threshold, or the top  few hundred descriptor pairs with the smallest pairwise distances are selected as  matched key points. </li> <li>Feature matching is done based on the feature distances computed previous by  taking the ratio of the best and second best match. 
  </li> <li>
 Homography matrix is needed to perform the transformation, and the  homography matrix requires at least 4 matches. Run RANSAC to estimate a  homography mapping one image onto the other.  </li><li> Use four matches to initialize the homography in each iteration. The output  should be a single transformation, H , that gets the most inliers in the course of all  the iterations.  </li><li> Warp one image onto the other using the estimated transformation.  </li><li> Create a new image big enough to hold the panorama and composite the two  images into it. </li><li> After aligning the images, the two images are blended seamlessly. Feathering is  used to smoothen the line of merging. This is done using cv2.addWeighted(), to  give weights for the right and left images and then merge then. In our  implementation, we used a window size of 10. </li>

 </ul>

</p>
