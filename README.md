# face-key-points-detection
# TOPIC<br/> 
To identify 15 landmark points on an gray scale image of a human face.

# Dataset<br/>
dataset used here is obtained from kaggle. it can be downloaded from <a href ="https://www.kaggle.com/c/facial-keypoints-detection/">here</a>. training dataset containes 7049 images and testing dataset contains about 1783 images. landmark keypoints of some of the images in the training set is missing.

<br/>

# Approach<br/>
CNN was used to solve this problem.<br/> 

1. using plain simple images <br/>


all the images which have missing landmark facial points were removed from the training dataset. CNN was trained on 1712 images and cross validated on 428 images . after training for about 420 epochs the validation_loss =.00029 and loss =.00072 and validation_mean_error = .0120

<br/>
2. with histogram equalization <br/> 
after histogram equalization of both the training and cross validation images, CNN was trained on the same training images.after 288 epochs validation loss on the same validation set was about .00039.model was not trained further


<br/>
3.missing key points <br/>
about 4909 images in the training data set has one or more missing land mark points.lets call these images incomplete images. CNN was first trained on the 1712 images for about 300 epochs and the the missing points were predicted. then they same model was trained on the combined datset. this does not lead to any improvemet in performance and the validation loss was fluctuating. this may be because the about 72% of the data were missing from the these incomplete images

<br/>
4. data augmentation <br/>
vertical and horizontal data augmentation were introducted on 1712 images in the training set and were cross validated on the same cross validation set of 428 images. after around 350 epochs the val_loss was .00034

<br/>

# performance<br/>
performance on the test set<br/>



