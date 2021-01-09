# Object-Detection

There are different types of object detection 

## Naive Approach 1 
1. Divide the image into patches 
2. Classify the patch 
3. Get the bounding boxes for the patches 

  ### Problem 
  Imperfect bounding boxes , they are not accurate
  ### Solution 
  Reduce the patch size
  
## Naive Approach 2 
1. Divide the image into patches with reduced siez 
2. Classify the patch 
3. Get the bounding boxes for the patches 

### Problem
Imperfect bounding boxed 
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
Highly computational 
Classify the blank patches



## So comes the Region based CNN
## R-CNN

 Generate Region Proposals ( Selective Search Algo ) -> Extract features using (AlexNet) -> Using features classification and localisation is done
 (Generate 2000 regions )                                ( iterates 2000 regions to 
                                                            extract the features)

## Fast-RCNN 

Input Image -> Feature extraction on whole image ( VGG16) -> ROI pooling -> map ROI pooling with feature extracted -> FC layer -> Classification and localisation 

## Faster-RCNN
Input Image -> Feature extraction on whole image ( Region Proposal Network RPN, 9 anchor boxes used ) -> ROI pooling -> map ROI pooling with feature extracted -> FC layer -> Classification and localisation 



## To combine the Region Proposal Network and ROI mapping  ** Single Stage Learning ** was introduced 
1) Yolo V1 
2) SDD 
3) Yolo V2 
4) Yolo V3 
