# 面试中常见的问题:running:

## 1. 聊聊项目

**1.1 最熟悉的项目（描述一下流程最全的项目）**

**1.2 金融风控中评分卡建模过程（以上补充）**

[1.1和1.2后期合并一下](../3_1_金融风控/评分卡算法建模流程.md)

**1.3 知识图谱（建图过程）**

**1.4 智能客服**

[智能客服项目流程](../3_3_文本处理/智能客服流程.md)

**1.5 催收机器人**

---

## 2. 项目workflow

 - 确定业务场景及目标
 - 理解实际问题，抽象为机器学习能处理的数学问题
    - 明确可以获得的数据
    - 机器学习的目标是分类、回归还是聚类
    - 算法评价指标：比如AUC, RMSE
 - 创建common sense baseline
 - 获取数据、分割数据(optional)
 - EDA
 - 预处理
 - 特征工程
 - 模型开发
 - 模型集成
 - 模型部署
 - 模型监控
 - 迭代

## 3. 经典的优化方法
 
 - [梯度下降法](https://zhuanlan.zhihu.com/p/36564434)
 - 牛顿法和拟牛顿法
 - 共轭梯度法(Adagrad, Adadelta, RMSprop, Adam)

## 4. 推导SVM算法

最大间隔超平面背后的原理：
 - 相当于在最小化权重时对训练误差进行了约束——对比 L2 范数正则化，则是在最小化训练误差时，对特征权重进行约束
 - 相当于限制了模型复杂度——在一定程度上防止过拟合，具有更强的泛化能力

推导看统计学习方法P100

## 5. 推导LR算法

看统计学习方法P78及<br>
[LR推导及代码实现（推荐）](https://zhuanlan.zhihu.com/p/36670444)

## 6. 看下决策树相关的知识点

西瓜书 4.1/4.2/4.3/4.4 <br>
统计学习方法 第五章

注意看下ID3, C4.5/C5.0的label都要是离散的，cart的label可以是连续的，
而且cart是回归树，后面用的默认的rf, xgb, lgb用的都是回归树

## 7. 类别不平衡问题

1. 欠采样 

代表算法：EasyEnsemble<br>
 - 首先通过从多数类中独立随机抽取出若干子集。
 - 将每个子集与少数类数据联合起来训练生成多个基分类器。
 - 最终将这些基分类器组合形成一个集成学习系统。

2. 过采样

代表算法：<br>

 - Bootstrap少数样本
 - SMOTE(Synthetic Minority Over-sampling Technique)
 - Borderline(SMOTE的一种提升方法)

[过采样参考网址](https://blog.csdn.net/a358463121/article/details/52304670)

3. 阈值移动

基于原始训练集进行学习，但在用训练好的分类器进行预测时，
将再缩放的公式y_new/(1-y_new)=y/(1-y)*(m+/m-) 嵌入到决策过程中，称为“阈值移动”。

## 8. 偏差和方差

泛化误差 = 偏差 + 方差 + 噪声

偏差：偏差度量了学习算法的期望预测与真实结果偏离程度，即刻画了学习算法本身的拟合能力<br>
方差：方差度量了同样大小的训练集的变动所导致的学习性能的变化，即刻画了数据扰动所造成的影响，或者说学习算法的稳定性

**8.1 过拟合即高方差，如何处理**

1. 增加样本数<br>
2. 降低模型的复杂度(CV)。比如决策树模型中降低树深度、进行剪枝等<br>
3. 加正则，使用正则化能够给模型的参数进行一定的约束，避免过拟合(损失函数上)<br>


---

面试总结参考网址：

[牛客网coding](https://www.nowcoder.com/ta/coding-interviews?page=1)

[lintcode](https://www.lintcode.com/problem/)

[牛客网sql](http://www.nowcoder.com/ta/sql)

[机器学习中你不可不知的几个算法常识](https://mp.weixin.qq.com/s/Fh-eQm41DI3rkKjEgC1Yig)

[机器学习、数据挖掘、数据分析岗面试总结](https://blog.csdn.net/Datawhale/article/details/81212235?from=singlemessage&isappinstalled=0)<br>

[机器学习项目流程](https://www.cnblogs.com/wxquare/p/5484690.html)

[Data Science Question Answer](https://github.com/ShuaiW/data-science-question-answer)

[别人的简历（参考）](https://cyc2018.github.io/page.html#next)
