## Plot Image With Clustering Information 

This is a plotting method used tto represent the way in which contours get clustered together into objects from [cluster_contour](cluster_contour.md).

**plantcv.visualize.clustered_contours**(*img, grouped_contour_indices, roi_objects, roi_obj_hierarchy, nrow=1, ncol=1*)

**returns** clustered_image

- **Parameters:**
    - img - RGB or grayscale image data for plotting.
    - grouped_contour_indices - Contour indices for which groups contours belong to. Output from [pcv.cluster_contour](cluster_contour.md)
    - roi_objects - object contours in an image that are needed to be clustered.
    - roi_obj_hierarchy - object hierarchy
    - nrow - Optional row grid lines to get drawn (default nrow=1). If `nrow` is unchanged, grid lines don't get drawn. 
    - ncol - Optional column grid lines to get drawn (default ncol=1). If `ncol` is unchanged, grid lines don't get drawn. 
- **Context:**
    - This function was written to allow users to debug [pcv.cluster_contour](cluster_contour.md) and make sure that contours from the same 
    plant are getting grouped together. 
- **Example use:**
    - Below

**Original image**

![Screenshot](img/tutorial_images/visualize_clustered_contours/multi_arabidopsis.jpg)

```python

from plantcv import plantcv as pcv

# Our input image was relatively large so increase global parameters 
pcv.params.text_size = 3 # Default = .55
pcv.params.text_thickness = 10 # Default = 2
pcv.params.line_thickness = 10 # Default = 5

# Create a figure using output from pcv.cluster_contours 
clustered_image = pcv.visualize.clustered_contours(img=img, grouped_contour_indices=cnt_i, 
                                                   roi_objects=roi_obj,
                                                   roi_obj_hierarchy=hier)

# Create a figure using output from pcv.cluster_contours with a grid
clustered_image = pcv.visualize.clustered_contours(img=img, grouped_contour_indices=cnt_i, 
                                                   roi_objects=roi_obj,
                                                   roi_obj_hierarchy=hier,
                                                   nrow=4, ncol=6)
                                       
```

**Clustered Image:** 

![Screenshot](img/documentation_images/visualize_clustered_contours/contour_cluster_img.jpg)

**Clustered Image with Grid:** 

![Screenshot](img/documentation_images/visualize_clustered_contours/contour_cluster_img_grid.jpg)