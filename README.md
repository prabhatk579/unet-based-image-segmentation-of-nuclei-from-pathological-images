<p align = center><font size = 10 color = brown>U-Net Based Image segmentation of Neuclei from Pathological Images</font></p>

Image segmentation is a technique of breaking down a digital image into several parts (sets of pixels, also known as image objects) in computer vision and digital Image processing. 
Image segmentation aims to simplify and transform an image’s representation into something more relevant and easier to evaluate. 
Image segmentation can find objects and boundaries (lines, curves, and so on) in photographs. Image segmentation produces segments encompass ing the entire image or a set of contours taken from the image. 
Every pixel in a segment has the same characteristic or computed feature, such as color, intensity, or texture. Adjacent areas have substantially varied colors when it comes to the exact attributes. Image segmentation can be used for Medical Imaging, object detection, pedestrian detection, face detection, brake light detection, locating objects in satellite images (roads, forests, crops, etc.), video surveillance, etc. 
U-Net technique is used for segmentation of the images. The images belong majorly from Medical Imaging Datasets and Object Detection dataset for Semantic Segmentation. We aim to train a model to differentiate various components present in an image with higher accuracy.

**The dataset used is [2018 Data Science Bowl](https://www.kaggle.com/c/data-science-bowl-2018) from kaggle.**

This dataset comprises a vast number of nucleus pictures that have been segmented. The pictures were taken under various circumstances and differences in cell type, magnification, and imaging modality (brightfield vs. fluorescence). The dataset is intended to test an algorithm’s generalization across these differences.

<img width="360" alt="image" src="https://user-images.githubusercontent.com/54438860/185107053-f36e98a7-f303-48ad-8b1a-28d774d224ee.png">

_Fig: Visual representation of dataset sample image and it's mask_

The dataset is divided into two parts. The training dataset has 670 folders containing two folders, namely “images” and “masks.” 
Masks contain the segmented masks of each nucleus. This folder is only included in the training set. The testing dataset has 65 folders.
Each folder has a unique identifier name. Each image has either one or more masks in the training dataset, i.e., Each mask contains one nucleus. Masks are not allowed to overlap (no pixel belongs to two masks). 
These masks are concatenated one after another into a single feature vector to recover the original image’s mask

<img width="440" alt="image" src="https://user-images.githubusercontent.com/54438860/185108291-01fa9401-7bd5-4adc-84ce-066ae2817a48.png">

_Fig: Concatenation of individual nucleus mask_

For masking of the cells we have used U-Net. The proposed U-Net model consists of five levels; the top four levels have one compression block and an expansion block. The bottom layer consists of one intermediate block. So, in total, the proposed U-Net model has four compression blocks, one intermediate block, and four expansion blocks.

<img width="440" alt="image" src="https://user-images.githubusercontent.com/54438860/185108790-35352cb2-f6b1-413a-8cee-72a7a81c27dd.png">

_Fig: Proposed U-Net architecture_

The results were as follows after training:

<img width="540" alt="image" src="https://user-images.githubusercontent.com/54438860/185109073-d737bf13-5c48-4cb6-8125-8fc1e7751f11.png">

_Fig: Comparison between the actual mask and the output of the model on training data_

<img width="360" alt="image" src="https://user-images.githubusercontent.com/54438860/185109231-27233d4b-0724-4a3e-a1bb-6162e9de9d26.png">

_Fig: The output of the model on a testing image_

<img width="360" alt="image" src="https://user-images.githubusercontent.com/54438860/185109414-06167a7e-3375-4367-ad30-a5c64db8b2e7.png">

_Fig: Model output on a dark image_



