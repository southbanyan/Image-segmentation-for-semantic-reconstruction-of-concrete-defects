# Concrete-Cracks-and-Spalling-Segmentation-using-U-Net
This code is used for image segmentation of concrete cracks and spalling. The U-Net network structure is built on tensorflow.

The images used to train the network were taken from PEER Hub Imagenet, which can be found at https://apps.peer.berkeley.edu/phi-net/
## Images Annotation
The training images were annotated using the image annotation tool __labelme__. Then, the annotated dataset was converted to PASCAL VOC format using a conversion tool. Detailed information can be found on this repository: https://github.com/wkentaro/labelme
## Getting Started
[train_val_split.ipynb](https://github.com/southbanyan/Concrete-Cracks-and-Spalling-Segmentation-using-U-Net/blob/main/train_val_split.ipynb): This notebook is used to split the training and validation datasets and generate a text file requested under the VOC format. In this project, 80% of the images is used as the training dataset, while 20% as the validation datasets. 

[image_segmentation_using_unet.ipynb](https://github.com/southbanyan/Concrete-Cracks-and-Spalling-Segmentation-using-U-Net/blob/main/image_segmentation_using_unet.ipynb): This notebook implements the segmentation of concrete cracks and spalling. It contains several functions such as image pre-processing, data augmentation, results prediction, etc. 

[Convexhull_Contours.ipynb](https://github.com/southbanyan/Concrete-Cracks-and-Spalling-Segmentation-using-U-Net/blob/main/Convexhull_Contours.ipynb): This notebook provides a new way of determining damage location. The predicted image is cut into smaller ones and convex hull detection is performed on them. After this, the small images are merged together to locate the damage. Finally, the damage contour coordinates are imported into the BIM model to detect and locate the damage to the building strcture. 
## Validation Results
After many experiments and tests, the average accuracy rate of validation can reach about __94%__.
