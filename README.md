# A Closer Look at Temporal Sentence Grounding in Videos: Datasets and Metrics

We present new splits of Charades-STA and ActivityNet Captions, called Charades-CD (Charades-STA under Changing Distributions) and ActivityNet-CD, respectively. These new splits are created by re-organizing all splits (i.e., the training, validation and test set) of original datasets, and the ground truth moment distributions are designed different in the training and test splits, i.e., out-of-distribution (OOD) testing. To better demonstrate the temporal sentence grounding models’ generalization ability and compare the performance between the OOD samples and the independent and identically distributed (IID) samples, we also maintain a test split with IID samples, denoted as test-iid (vs. test-ood). 

### The statistics of the original and our re-organized datasets are as follows:
![](https://github.com/yytzsy/grounding_changing_distribution/blob/main/statistics.jpg)

To demonstrate the difficulty of the new proposed splits (i.e., Charades-CD and ActivityNet-CD), we compare the performance of two simple baselines and eight state-ofthe-art methods on both the original and proposed splits. 
* Bias-based method: it uses the gaussian kernel density estimation to fit the moment annotation distribution, and randomly samples several locations based on the fitted distribution as the moment predictions. 
* PredictAll method: it directly predicts the whole video as the moment predictions.
* CTRL
* ACRN
* ABLR
* SCDM
* 2D-TAN
* DRN
* TSP-PRL
* WSSL 
