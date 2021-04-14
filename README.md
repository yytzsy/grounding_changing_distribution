# A Closer Look at Temporal Sentence Grounding in Videos: Datasets and Metrics

## Introduction

We present new splits of Charades-STA and ActivityNet Captions, called Charades-CD (Charades-STA under Changing Distributions) and ActivityNet-CD, respectively. These new splits are created by re-organizing all splits (i.e., the training, validation and test set) of original datasets, and the ground truth moment distributions are designed different in the training and test splits, i.e., out-of-distribution (OOD) testing. To better demonstrate the temporal sentence grounding models’ generalization ability and compare the performance between the OOD samples and the independent and identically distributed (IID) samples, we also maintain a test split with IID samples, denoted as test-iid (vs. test-ood). 

## Dataset Statistics
![](https://github.com/yytzsy/grounding_changing_distribution/blob/main/statistics.jpg)

## Compared Methods
To demonstrate the difficulty of the new proposed splits (i.e., Charades-CD and ActivityNet-CD), we compare the performance of two simple baselines and eight state-ofthe-art methods on both the original and proposed splits. 

* Bias-based method: it uses the gaussian kernel density estimation to fit the moment annotation distribution, and randomly samples several locations based on the fitted distribution as the moment predictions. 
* PredictAll method: it directly predicts the whole video as the moment predictions.
* [CTRL](https://github.com/jiyanggao/TALL)
* [ACRN](https://sigir2018.wixsite.com/acrn)
* [ABLR](https://github.com/yytzsy/ABLR_code)
* [SCDM](https://github.com/yytzsy/SCDM)
* [2D-TAN](https://github.com/microsoft/2D-TAN)
* [DRN](https://github.com/Alvin-Zeng/DRN)
* [TSP-PRL](https://github.com/WuJie1010/TSP-PRL)
* [WSSL](https://github.com/XgDuan/WSDEC)

For all these SOTA methods, we use the public official implementations to get their temporal grounding results. The results of the proposed test-iid and test-ood sets on two
datasets come from the same model finetuned on their respective val set. For more fair comparisons, we have unified the feature representations of the videos and sentence queries. To cater for most of TSGV methods, we use [I3D feature](https://cloud.tsinghua.edu.cn/f/b17bc7e9f17b4d0f8179/?dl=1) for the videos in Charades-STA (Charades-CD), and [C3D feature](https://cloud.tsinghua.edu.cn/d/8cc1ca07bd3642e2972e/) (The video feature file is too big to upload, and we have divided it into 10 parts. You should merge the 10 parts to one whole file and use it for model training.) for the videos in ActivityNet Captions (Activity-CD). Each word in the query sentences is encoded by a [GloVe](http://nlp.stanford.edu/data/glove.840B.300d.zip) word representation.

## Results

We report the performance of all mentioned TSGV methods with metric R@1,IoU@0.7 in the figure below. From this figure, we can observe that almost all methods have a significant
performance gap between the test-iid and test-ood sets, i.e., these methods always over-rely on the moment annotation biases, and fail to generalize to the OOD test set. Meanwhile, the performance results on the original test set and the proposed test-iid set are relatively close, because the moment distribution of the test-iid set is still similar to the majority of the whole dataset.
![](https://github.com/yytzsy/grounding_changing_distribution/blob/main/performance.jpg)
