# Image segmentation for semantic reconstruction of concrete defects
This code is used for image segmentation of concrete cracks and spalling. The U-Net network structure is built on tensorflow. After segmentation, a semantic reconstruction is performed and defects are transferred to BIM object using Industry Foundation Classes (IFC) [Buildingsmart](https://standards.buildingsmart.org/IFC/RELEASE/IFC4/ADD2_TC1/HTML/) and [IfcOpenShell](https://ifcopenshell.org/). 

The images used to train the network were taken from PEER Hub Imagenet, which can be found at https://apps.peer.berkeley.edu/phi-net/

## Images Annotation
The training images were annotated using the image annotation tool __labelme__. Then, the annotated dataset was converted to PASCAL VOC format using a conversion tool. Detailed information can be found on this repository: https://github.com/wkentaro/labelme. 

## Getting Started
The Dataset needs to be split into samples for training and validation. Our dataset here is split already 80 % / 20 %. If you want to use your own data or split the dataset differently you can use [train_val_split.ipynb](train_val_split.ipynb). This notebook is used to split the training and validation datasets and generate a text file requested under the VOC format. In this project, 80% of the images is used as the training dataset, while 20% as the validation datasets. 

[image_segmentation_using_unet.ipynb](image_segmentation_using_unet.ipynb): This notebook implements the segmentation of concrete cracks and spalling. It contains several functions such as image pre-processing, data augmentation, results prediction, etc. 

[Convexhull_Contours.ipynb](Convexhull_Contours.ipynb): This notebook provides a new way of determining damage location. The predicted image is cut into smaller ones and convex hull detection is performed on them. After this, the small images are merged together to locate the damage. Finally, the damage contour coordinates are imported into the BIM model to detect and locate the damage to the building strcture. 
## Validation Results
In our experiments and tests, an average accuracy rate of __94%__ during validation could be achieved. 

## Creating IFC damage objects
[ifc_damage.ipynb](ifc_damage.ipynb): After the contour was estimated, the defects are transferred to BIM objects. As there is no information about the global position of the defect and other objects in the dataset, defects are placed on a simple wall for reference. 
