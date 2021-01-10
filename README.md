# Object-Detection

There are different types of object detection 

## Naive Approach 1 
1. Divide the image into patches \
2. Classify the patch \
3. Get the bounding boxes for the patches \

  ### Problem 
  Imperfect bounding boxes , they are not accurate
  ### Solution 
  Reduce the patch size
  
## Naive Approach 2 
1. Divide the image into patches with reduced size \
2. Classify the patch \
3. Get the bounding boxes for the patches \

### Problem
Imperfect bounding boxed \
Two boxes may detected the object
### Solution
Different Shape patches 

## Naive Approach 3 

To overcome the Naive approach 2 problem, we have naive approach 3 that has different patch sizes 

### Problem 
Object of different Orientation 
### Solution 
Anchor boxes 


## Naive Appproach 4

Here we use anchor boxes to detect different orientation 

### Problem 
Highly computational \
Classify the blank patches


  
## So comes the Region based CNN
## R-CNN

 Generate Region Proposals ( Selective Search Algo ) -> Extract features using (AlexNet) -> Using features classification and localisation is done \
 
 (Generate 2000 regions )   ( iterates 2000 regions to extract the features)

## Fast-RCNN 

Input Image -> Feature extraction on whole image ( VGG16) -> ROI pooling -> map ROI pooling with feature extracted -> FC layer -> Classification and localisation 

## Faster-RCNN
Input Image -> Feature extraction on whole image ( Region Proposal Network RPN, 9 anchor boxes used ) -> ROI pooling -> map ROI pooling with feature extracted -> FC layer -> Classification and localisation 



## To combine the Region Proposal Network and ROI mapping  ** Single Stage Learning ** was introduced 
1) Yolo V1  \
   Divides image 7x7 grid -> useses DarkNet 16 architecture -> Sliding Window approach -> Non max Suppression to reduce the bounding boxes 
  
2) SDD  \
   Uses VGG16 architecture  + other CONV layer ->  Image Pyramid Network ->  Non max suppression \
   output - 2BB(10) rest 20 ( classes ) 
3) Yolo V2  \ 
Image grid 13 x 13 -> uses darknet 19 architecture - CONV and Batch Normalisation layers are used -> More than 2 Bounding boxes
4) Yolo V3  \
Multi classification -> Darknet 53 + other 53  layer ( totak 106  layers ) - Feature Pyramid network -> uses features of different scale to predict the o/p. \
Slower than yolo v2 but more accurate  \
High performance on smaller objects  

5) RetinaNet \
Faster-RCNN's AP ( Average Precison ) is better than one stage network. \
Overcomes the class imbalance of yolo V2 & V3 ( background classes & object classes ) \
Uses **Focal Loss** function to overcome the class imbalance 
**When object is easy to detect, the probability is high and loss is down weighted ** \
**When the object is hard to detect, the probability is low and loass is unaffected **

When the object

