# face-key-points-detection
# TOPIC<br/> 
To identify 15 landmark points on an gray scale image of a human face.

# Dataset<br/>
dataset used here is obtained from kaggle. it can be downloaded from <a href ="https://www.kaggle.com/c/facial-keypoints-detection/">here</a>. training dataset containes 7049 images and testing dataset contains about 1783 images of size 96*96. landmark keypoints of some of the images in the training set is missing.

<br/>

# Approach<br/>
CNN was used to solve this problem
## 1. using plain simple images
all the images which have missing landmark facial points were removed from the training dataset. CNN was trained on 1712 images and cross validated on 428 images . after training for about 420 epochs the <b> validation_loss =.00029 </b> and <b> loss =.00072 </b> and <b> validation_mean_error = .0120 </b>

## 2. with histogram equalization 
after histogram equalization of both the training and cross validation images, CNN was trained on the same training images.after 288 epochs validation loss on the same validation set was about <b> .00039 </b>.model was not trained further



## 3.missing key points 
about 4909 images in the training data set has one or more missing land mark points.lets call these images incomplete images. CNN was first trained on the 1712 images for about 300 epochs and the the missing points were predicted. then they same model was trained on the combined datset. this does not lead to any improvemet in performance and the validation loss was fluctuating. this may be because the about <b> 72% </b> of the data were missing from the these incomplete images

## 4. data augmentation 
vertical and horizontal data augmentation were introducted on 1712 images in the training set and were cross validated on the same cross validation set of 428 images. after around <b> 350 </b> epochs the val_loss was .00034

<br/>

# performance<br/>
performance on the test set<br/>



