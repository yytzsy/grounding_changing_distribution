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
datasets come from the same model finetuned on their respective val set. For more fair comparisons, we have unified the feature representations of the videos and sentence queries. To cater for most of TSGV methods, we use [I3D feature]((https://drive.google.com/file/d/1P-kfWOQoHzSxd8vNpogNGyx8Jc4TKj4E/view?usp=sharing)) for the videos in Charades-STA (Charades-CD), and [C3D feature](https://drive.google.com/file/d/1X8GT1MohStPfaoTlDiuzZAHkas5Qt3t8/view?usp=sharing) for the videos in ActivityNet Captions (Activity-CD). Each word in the query sentences is encoded by a [GloVe](http://nlp.stanford.edu/data/glove.840B.300d.zip) word representation.

## Results


