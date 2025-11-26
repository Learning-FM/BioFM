# 可穿戴信号的基础模型建模范式算法研究综述



## 摘要

基础模型的快速发展从根本上重塑了可穿戴生理序列建模范式，并在多种下游任务中带来了显著性能提升。这类方法通常通过预训练或微调基础模型，以获取能够迁移至心电图、脑电图、惯性测量单元、光电容积描记以及多类可穿戴感知信号等生理序列任务的泛化知识。这些生理序列构成了人体生理与行为“语言”，在多种临床环境中具有丰富的诊断与预后价值。本综述旨在对可穿戴生理序列基础模型提供全面、系统且最新的研究脉络总结。尽管已有综述分别从医疗影像方面、时间序列方面以及生理信号数据层面对基础模型进行了讨论，但仍缺乏对方法论范式的核心机制的深入剖析，即基础模型为何能够在可穿戴生理序列任务中发挥作用，以及其背后如何实现有效提升。为弥补这一空白，本文采用方法学范式为核心的分类视角，对可穿戴生理序列基础模型的关键组成要素进行系统化全景梳理，包括：基础模型的演化，模型架构，预训练范式，适配范式，数据模态以及应用场景等，进一步地，我们选取了不同预训练范式在四类不同领域数据集（ECG，EEG，IMU，EOG）上开展了大规模的实验，系统地分析了不同预训练策略对可穿戴序列的优势与不足。



<p align="center">
    <img src="pictures/framework.jpg" width="1000" align="center">
</p>


## Datasets
The datasets used in this project are as follows:
### Time-Series Classification
* [128 UCR datasets](https://www.cs.ucr.edu/~eamonn/time_series_data_2018/UCRArchive_2018.zip)
* [30 UEA datasets](http://www.timeseriesclassification.com/Downloads/Archives/Multivariate2018_arff.zip)
* [SleepEEG dataset](https://www.physionet.org/content/sleep-edfx/1.0.0/) 
* [Epilepsy dataset](https://repositori.upf.edu/handle/10230/42894) 
* [FD-A and FD-B datasets](https://mb.uni-paderborn.de/en/kat/main-research/datacenter/bearing-datacenter/data-sets-and-download) 
* [HAR dataset](https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones) 
* [Gesture dataset](http://www.timeseriesclassification.com/description.php?Dataset=UWaveGestureLibrary) 
* [ECG dataset](https://physionet.org/content/challenge-2017/1.0.0/) 
* [EMG dataset](https://physionet.org/content/emgdb/1.0.0/) 

### Time-Series Forecasting
* [ETDataset (including 4 datasets)](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014)
* [Electricity](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014)
* [Traffic](http://pems.dot.ca.gov)
* [Weather](https://www.bgc-jena.mpg.de/wetter)
* [Exchange](https://github.com/laiguokun/multivariate-time-series-data)
* [ILI](https://gis.cdc.gov/grasp/fluview/fluportaldashboard.html)

### Time-Series Anomaly Detection
* [Yahoo dataset](https://webscope.sandbox.yahoo.com/catalog.php?datatype=s&did=70) 
* [KPI dataset](http://test-10056879.file.myqcloud.com/10056879/test/20180524_78431960010324/KPI%E5%BC%82%E5%B8%B8%E6%A3%80%E6%B5%8B%E5%86%B3%E8%B5%9B%E6%95%B0%E6%8D%AE%E9%9B%86.zip)
* [250 UCR anomaly detection datasets](https://wu.renjie.im/research/anomaly-benchmarks-are-flawed/#ucr-time-series-anomaly-archiv) 
* [MSL dataset](https://github.com/khundman/telemanom) 
* [SMAP dataset](https://github.com/eBay/RANSynCoders) 
* [PSM dataset](https://github.com/khundman/telemanom) 
* [SMD dataset](https://github.com/NetManAIOps/OmniAnomaly) 
* [SWaT dataset](https://itrust.sutd.edu.sg/itrust-labs_datasets/dataset_info/#swat) 
* [NIPS-TS-SWAN dataset](https://github.com/datamllab/tods/tree/benchmark/benchmark) 
* [NIPS-TS-GECCO dataset](https://github.com/datamllab/tods/tree/benchmark/benchmark) 



## Pre-Trained Models on Time Series Classification
- [x] [FCN](https://github.com/cauchyturing/UCR_Time_Series_Classification_Deep_Learning_Baseline)
- [x] [FCN Encoder+CNN Decoder](https://github.com/qianlima-lab/time-series-ptms/blob/master/ts_classification_methods/model/tsm_model.py)
- [x] [FCN Encoder+RNN Decoder](https://github.com/qianlima-lab/time-series-ptms/blob/master/ts_classification_methods/model/tsm_model.py)
- [x] [TCN](https://github.com/White-Link/UnsupervisedScalableRepresentationLearningTimeSeries)
- [x] [Transformer](https://github.com/gzerveas/mvts_transformer)
- [x] [TST](https://github.com/gzerveas/mvts_transformer)
- [x] [T-Loss](https://github.com/White-Link/UnsupervisedScalableRepresentationLearningTimeSeries)
- [x] [SelfTime](https://github.com/haoyfan/SelfTime)
- [x] [TS-TCC](https://github.com/emadeldeen24/TS-TCC)
- [x] [TS2Vec](https://github.com/zhihanyue/ts2vec)
- [x] [TimesNet](https://github.com/thuml/TimesNet)
- [x] [PatchTST](https://github.com/yuqinie98/PatchTST)
- [x] [GPT4TS](https://github.com/DAMO-DI-ML/NeurIPS2023-One-Fits-All)

For details, please refer to [ts_classification_methods/README](https://github.com/qianlima-lab/time-series-ptms/blob/master/ts_classification_methods/README.md).

## Pre-Trained Models on Time Series Forecasting

- [x] [LogTrans](https://github.com/AIStream-Peelout/flow-forecast)
- [x] [TCN](https://github.com/locuslab/TCN)
- [x] [Informer](https://github.com/zhouhaoyi/Informer2020)
- [x] [Autoformer](https://github.com/thuml/autoformer)
- [x] [TS2Vec](https://github.com/zhihanyue/ts2vec)
- [x] [CoST](https://github.com/salesforce/CoST)
- [x] [TimesNet](https://github.com/thuml/TimesNet)
- [x] [PatchTST](https://github.com/yuqinie98/PatchTST)
- [x] [DLinear](https://github.com/vivva/DLinear)
- [x] [GPT4TS](https://github.com/DAMO-DI-ML/NeurIPS2023-One-Fits-All)
- [x] [TEMPO](https://github.com/DC-research/TEMPO)
- [x] [iTransformer](https://github.com/thuml/iTransformer)

For details, please refer to [ts_forecating_methods/README](https://github.com/qianlima-lab/transfer-to-transformer-tsm/blob/master/ts_forecasting_methods/README.md).

## Pre-Trained Models on Time Series Anomaly Detection

- [x] [SPOT](https://github.com/limjcst/ads-evt)
- [x] [DSPOT](https://github.com/limjcst/ads-evt)
- [x] [LSTM-VAE](https://github.com/SchindlerLiang/VAE-for-Anomaly-Detection)
- [x] [DONUT](https://github.com/NetManAIOps/donut)
- [x] [Spectral Residual (SR)](https://dl.acm.org/doi/10.1145/3292500.3330680)
- [x] [Anomaly Transformer (AT)](https://github.com/spencerbraun/anomaly_transformer_pytorch)
- [x] [TS2Vec](https://github.com/zhihanyue/ts2vec)
- [x] [TimesNet](https://github.com/thuml/TimesNet)
- [x] [GPT4TS](https://github.com/DAMO-DI-ML/NeurIPS2023-One-Fits-All)
- [x] [DCdetector](https://github.com/DAMO-DI-ML/KDD2023-DCdetector)

For details, please refer to [ts_anomaly_detection_methods/README](https://github.com/qianlima-lab/transfer-to-transformer-tsm/blob/master/ts_anomaly_detection_methods/README.md).

## Acknowledgments
We thank the anonymous reviewers for their helpful feedback. We thank Professor **Eamonn Keogh** from UCR and all the people who have contributed to the UCR\&UEA time series archives and other time series datasets. The authors would like to thank 
Professor **Garrison W. Cottrell** from UCSD, and **Chuxin Chen**, **Xidi Cai**, **Yu Chen**, and **Peitian Ma** from SCUT for the helpful suggestions. 

## Citation
If you use this code for your research, please cite our paper:
```
@article{ma2024survey,
  title={A survey on time-series pre-trained models},
  author={Ma, Qianli and Liu, Zhen and Zheng, Zhenjing and Huang, Ziyang and Zhu, Siying and Yu, Zhongzhong and Kwok, James T},
  journal={IEEE Transactions on Knowledge and Data Engineering},
  year={2024}
}
```
