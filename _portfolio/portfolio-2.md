---
title: "Class Project of ML at SZU"
excerpt: "Use pre-trained ResNet-18 to do a classification first for training, then use the well-trained model to do a matching task<br/><img src='/images/palmvein_500x300.png'>"
collection: portfolio
---
[Paper in Chinese](https://ianzou2000.github.io/files/%E5%A4%A7%E4%BD%9C%E4%B8%9A%E8%AE%BA%E6%96%87_%E9%82%B9%E6%9D%B0_2019193009.pdf)

[Code](https://github.com/ianzou2000/palm-vein-recognization-using-ResNet18-SZU)

## Abstract
Currently, palm vein and palmprint recognition technologies have received high attention from researchers, resulting in rapid development and significant breakthroughs in this field. This article uses a fine-tuned convolutional neural network-based method to recognize and match palm veins and palmprints. Specifically, a pre-trained ResNet18 model is used, and the parameters before layer4 are frozen for training and testing palm vein and palmprint recognition. When making predictions, the feature matrix output by the model is transformed into a feature vector, and the cosine similarity is calculated pairwise. The image with the highest similarity to the matching object is considered to belong to the same person.

In this article, the TJU-P palmprint dataset and PolyU M_N palm vein dataset are used for training and testing, respectively, achieving good results of 100% training accuracy, 90.2% top-1 recognition rate, and 95.78% top-5 recognition rate; as well as 100% training accuracy, 97% top-1 recognition rate, and 99% top-5 recognition rate. For prediction, 495 categories are selected from the PolyU M_N palm vein dataset for training and testing, and 60 samples from 5 categories are matched pairwise. After multiple rounds of tuning and comparison, the optimal similarity threshold δ=0.9718 is selected based on accuracy priority and AUC consideration, achieving a final matching accuracy of 96% with AUC=0.93. Then, all 500 categories in the PolyU M_N palm vein dataset are used for training and testing, and 30 validation sets are used for prediction. After dozens of experiments, the optimal similarity threshold δ=0.99465 is selected, achieving a final matching accuracy of 99% with AUC=0.87.

Furthermore, discussions and visual analyses are conducted on the optimal parameter selection for image enhancement methods, batch sizes, and whether to select ROI regions. Among the image enhancement methods of histogram equalization, CLAHE, Laplacian, and log transformation, histogram equalization (hist) performs the best. Among batch sizes of 8, 16, 32, 64, and 128, batch size=8 has the fastest convergence rate. Regarding whether to select ROI regions, not selecting them is more conducive to feature recognition and extraction, resulting in higher accuracy compared to simply cropping the original image.

## key words
Palm Vein Matching, Palm Print Matching, Transfer Learning, Convolutional Neural Network, ResNet18
