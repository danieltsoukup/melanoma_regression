# Logistic regression on images and why it can (accidentally) work

The goal of this notebook is to look into why one of the simplest classification models, logistic regression, might give surprisingly good results on raw image data. We work with data from [Kaggle](https://www.kaggle.com/fanconic/skin-cancer-malignant-vs-benign), originally sourced under the [ISIC competitions](https://www.isic-archive.com/#!/topWithHeader/tightContentTop/challenges).


<img src="assets/pixel_std.png" 
alt="tsne clustering"/>

**TLDR**: Logistic Regression achieves 71% test accuracy on the malignant/benign classification task out of the box, based on b/w images and balanced data. To investigate how is this possible, we look at various pixel statistics and feature importances and arrive at the conclusion that pixel intensity at the corner of the images provide a strong predictor for the target.


