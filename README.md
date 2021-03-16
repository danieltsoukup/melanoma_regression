# Logistic regression on images and why it can (accidentally) work

This mini project was motivated by seeing in [this](https://www.kaggle.com/niteshx2/melanoma-starter-simplest-explanation-and-model/comments) and [this notebook](https://www.kaggle.com/wrecked22/skin-cancer-detection-using-cnn-83-31-accuracy) that one of the simplest classification models, logistic regression, on raw image features gives on-par performance with vanilla CNNs. We'll look into why this might be the case. 

The data we use here comes from [Kaggle](https://www.kaggle.com/fanconic/skin-cancer-malignant-vs-benign), originally sourced under the [ISIC competitions](https://www.isic-archive.com/#!/topWithHeader/tightContentTop/challenges). Here is a sample from our training set, 10 benign and 10 malignant images:



<img src="assets/benign_sample.png" 
alt="benign images"/>

<img src="assets/malignant_sample.png" 
alt="malignant images"/>

**TLDR**: Logistic Regression achieves 71% test accuracy on the malignant/benign classification task out of the box, based on b/w images and balanced data. To investigate how this is possible, we look at various pixel statistics and feature importance measures and arrive at the conclusion that (for this data set) pixel intensity at the corner of the images provides a strong predictor for the target.


<img src="assets/pixel_std.png" 
alt="pixel variance"/>