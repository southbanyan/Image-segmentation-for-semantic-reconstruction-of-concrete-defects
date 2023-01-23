# Concrete-Cracks-and-Spalling-Segmentation-using-U-Net
This code is used for image segmentation of concrete cracks and spalling. The U-Net network structure is built on tensorflow. 
The images used to train the network were taken from PEER Hub Imagenet, which can be found at https://apps.peer.berkeley.edu/phi-net/
## Images Annotation
The training images were annotated using the image annotation tool __labelme__. Then, the annotated dataset was converted to PASCAL VOC format using a conversion tool. Detailed information can be found on this repository: https://github.com/wkentaro/labelme
