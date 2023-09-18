# Unsupervised Defect Detection for Cutting Tool Images using Deep Learning

# 1 Dataset Collection
The cutting tool images used in this project were provided by Siemens FMP- Smart Manufacturing Lab. 
The dataset comprises both defective and non-defective images of cutting tools.

# 2 Preprocessing
Images undergo preprocessing using OpenCV to enhance their quality:

Noise removal
Contrast and brightness enhancement
Image sharpening using erosion and dilation
Resizing images for consistent input to models

# 3 Image Segmentation
The RITM (Reviving Iterative Training with Mask Guidance for Interactive Segmentation) model, a deep learning model, 
is employed to segment non-defective images into foreground and background. 
This model facilitates segmentation without the necessity of annotations. It’s based on a modified U-Net architecture.

# 4 Generating Superpixel
Superpixel Sampling Network (SSN) is used to create superpixels from segmented images.
Superpixels are coherent, neighboring regions in an image with similar visual characteristics. 
The SSN model classifies each superpixel into three categories: background, wear, or tool.

# 5 Comparing Superpixels
Deep metric learning compares new defected images against a reference dataset. 
It's trained using the reference dataset, and a similarity metric is computed between the new defected image and the reference dataset.
