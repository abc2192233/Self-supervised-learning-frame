# Self-supervised-learning-frame
It is a Self-supervised learning frame interpret and some notes.


## Background
由于最近着手的项目需要设计一套预测平台的系统架构，故在此记录一些心得还有设想

## Part 1 整体架构

参考了facebook人工智能实验室的Large-scale forecasting: Self-supervised learning framework for hyperparameter tuning一文中的自监督学习框架

![image](frame_img/Lark20210617-144451.png)
<p align="center">Workflow of Self-Supervised Learning for Hyper-Parameter Tuning (SSL-HPT)</p>


    在运维系统中，由于业务场景较为单一，相对环境干涉因素影响较小，大部分数值异常波动源于人为操作，在一期项目中预计采用Prophet及LSTM和ARIMA作为Time Series数据流处理算法，通过基于HPT（Hyper-parameter tuning超参数调试）在默认搜索空间内对各个处理算法结果进行最优选取。

    在各预测算法结果被最优选择后，进行聚合横向对比分析，根据具体外部环境（集群性能、数据规模与预测区间等）筛选出最优模型。

    在模型建立之后，将Time Series选出一部分特征作为输入项训练出自监督学习模型，根据分类器给出的特征加入至模型，对后续输入的New Time Series进行预测。
