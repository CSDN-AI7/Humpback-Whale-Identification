# 座头鲸识别 --`kaggle`

## 描述

​	经过几个世纪的频繁捕鲸，鲸鱼种群数量正在减少，一方面他们很难适应变暖的海洋，另一方面他们的食物--小鱼小虾～每天也都要被渔业工作者抢走很多。

​	为了帮助开展鲸鱼的保护工作，科学家们使用照片监控系统来监测海洋活动。他们依靠鲸鱼尾巴的形状和镜头中的独特标记来识别他们正在分析的鲸鱼种类，并精心记录鲸鱼的动态和运动。在过去的40年里，大部分工作都由个别科学家手工完成，留下了大量未开发和未充分利用的数据。

​	在本次比赛中，您面临的挑战是建立一种算法来识别图像中的个体鲸鱼。您将分析`Happywhale`的数据库，其中包含来自研究机构和公共贡献者的超过25,000张图像，通过此次比赛，您所做的一切都将有助于对全球海洋哺乳动物种群动态的研究。

请注意，此竞赛在本质上与[此竞赛](https://www.kaggle.com/c/whale-categorization-playground)类似，具有扩展和更新的数据集。

我们要感谢[Happywhale](https://happywhale.com/)提供这些数据和问题。`Happywhale`是一个平台，它使用图像处理算法来识别人们递交的鲸鱼照片。



## 评估

### 评价指标

要求使用 Mean Average Precision @ 5 (MAP@5):

$MAP@5= \frac1U∑_{u=1}^U∑_{k=1}^{min(n,5))}P(k)$



### 提交文件

对于 测试集中的每个图片，您最多可以预测5个鲸鱼标签`id`。如果图片中的鲸鱼没有被归类到训练集中的其中任意一种，那么该鲸鱼应该被标记为`new_whale`。最后上传的文件应当含有表头，并采用如下格式：

```
Image,Id 
00028a005.jpg,new_whale w_23a388d w_9b5109b w_9c506f6 w_0369a5c 
000dcf7d8.jpg,new_whale w_23a388d w_9b5109b w_9c506f6 w_0369a5c 
...
```



## 时间安排

- **2019**  年**2月21日** - 报名截止日期。您必须在此日期之前接受竞赛规则才能参加比赛。
- **2019**  年**2月21日** - 团队合并截止日期。这是参与者加入或合并团队的最后一天。
- **2019**年**2月21日** - 外部数据披露截止日期。竞赛中使用的所有外部数据必须在此日期之前在论坛中公布。
- **2019**  年**2月28日** - 最终提交截止日期。

除非另有说明，所有截止日期均为相应日期的`UTC`时间晚上11:59。比赛组织者保留在认为必要时更新比赛时间表的权利。



## 奖励

- **1st Place** - $10,000
- **2nd Place** - $7,500
- **3rd Place** - $ 2,500
- **4th Place** - $ 2,500
- **5th Place** - $ 2,500



## 数据与数据文件说明

#### 数据描述

数据总大小约为`6G`，训练数据包含数以千计的座头鲸图像。每一个鲸鱼图片都已经被研究人员鉴定并给予了`Id`。挑战在于预测测试集中图像里面鲸鱼的`Id`。任务难点在于，我们有`3000`多鲸鱼`Id`，但是每一种只有少数的几个例子。

#### 文件说明

- **`train.zip`** - 包含训练图片的文件夹
- **`train.csv`** - 将训练图片映射到到适当的鲸鱼`Id`。未在训练数据中识别出标签的鲸鱼应标记为`new_whale`。
- **`test.zip`** - 包含测试图片的文件夹，用于预测鲸鱼`Id`
- **`sample_submission.csv`** - 提交文件的正确格式示例

> 数据已经下载完毕，稍后分享在百度云盘中，也可以用稍后介绍的`kaggle`官方`API`来下载，巨快无比。



#### 其他说明

**竞赛题目** (the 'Competition'): `Humpback Whale Identification`

**竞赛赞助商**: `HappyWhale`

**竞赛赞助商地址**: 425 SE 11th Ave, Portland, Oregon US

**竞赛网址**: <https://www.kaggle.com/c/humpback-whale-identification>

> 在竞赛官网有详细规则，例如管制地区，获奖队伍义务，奖金平均分配等政策，可以去看看。



### 一些资料

1.https://www.kaggle.com/ckanth090/kernel-for-whales   

2.https://www.kaggle.com/kretes/eda-whale-dists-images-and-resolutions

3.https://www.kaggle.com/c/whale-detection-challenge (Marinexplore and Cornell University的鲸鱼识别挑战赛（已结束）)

4.https://www.kaggle.com/c/noaa-right-whale-recognition/discussion/18409（右鲸识别项目第一名的解决方案）

5.https://www.kaggle.com/c/noaa-right-whale-recognition/discussion（右鲸识别项目排行榜）



# `kaggle API`的安装使用

> 参见https://github.com/Kaggle/kaggle-api

1.使用`pip3 install kaggle`命令直接安装

> 如果系统中有`python2`，那么`pip`指向`python2`，请使用`pip3`安装.



2.在[https://www.kaggle.com上](https://www.kaggle.com/)注册`Kaggle`帐户。转到用户个人资料的“帐户”标签，然后选择“创建`API`令牌”，即：

https://www.kaggle.com ➡️ User Ranking ➡️ API ➡️ Create New API Token

> 这将触发下载`kaggle.json`，其中包含`API`凭据的文件。将此文件放在该位置`~/.kaggle/kaggle.json`
>
> （Windows上在`C:\Users\<Windows-username>\.kaggle\kaggle.json`-   



3.用下面的命令赋予使用权限：

```
chmod 600 ~/.kaggle/kaggle.json
```



4.还可将`Kaggle`用户名和令牌添加到环境中：

注：这两个内容在刚才下载的`json`文件中。

```
export KAGGLE_USERNAME = datadinosaur
 export KAGGLE_KEY = xxxxxxxxxxxxxx
```





5.`kaggle API` 的具体命令请见上面的`github`地址，可以很方便的拉取数据，获取排名，递交结果等。

这里贴出我们这个项目的数据下载命令，下载好的数据自动放在`~/.kaggle`目录中

> （Windows上在`C:\Users\<Windows-username>\.kaggle



```bash
kaggle competitions download -c humpback-whale-identification
```

