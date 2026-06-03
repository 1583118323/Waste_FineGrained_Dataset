# 城市生活垃圾细粒度分类数据集
版本：1.0 | 发布日期：2025-12-20 | 许可证：CC0 1.0 Universal

## 一、数据集概述
本数据集为**城市生活垃圾细粒度分类数据集**，针对轻量化视觉语言模型在垃圾分类任务中的研究需求构建，包含8类常见生活垃圾的240张标注图片，按8:2比例划分为训练集（192张）和验证集（48张）。

本数据集适配论文《面向形态多变垃圾的轻量化视觉语言模型细粒度分类方法研究》的研究需求，可用于模型训练、泛化能力验证、对比实验等场景。

## 二、数据集结构
```
Waste_FineGrained_Dataset/
├── images
│   ├── train/                # 训练集图片
│   │   ├── aluminum_can
│   │   ├── newspaper
│   │   ├── packaging_bag
│   │   ├── paper_box
│   │   ├── plastic_bottle
│   │   ├── plastic_box
│   │   ├── Surgical_mask
│   │   └── toilet_paper
│   └── val/                  # 验证集图片
│       ├── aluminum_can
│       ├── newspaper
│       ├── packaging_bag
│       ├── paper_box
│       ├── plastic_bottle
│       ├── plastic_box
│       ├── Surgical_mask
│       └── toilet_paper
└── labels
├── train_labels.csv
└── val_labels.cs
```
### CSV标注字段说明
|字段|说明|
|----|----|
|image_path|图片相对路径|
|answer|中文垃圾类别|

## 三、类别与样本统计
| 英文类别名 | 中文类别名 | 训练集样本数 | 验证集样本数 | 总样本数 |
|------------|------------|--------------|--------------|----------|
| aluminum_can | 易拉罐 | 24 | 6 | 30 |
| newspaper | 报纸 | 24 | 6 | 30 |
| packaging_bag | 塑料袋 | 24 | 6 | 30 |
| paper_box | 纸盒 | 24 | 6 | 30 |
| plastic_bottle | 塑料瓶 | 24 | 6 | 30 |
| plastic_box | 塑料盒 | 24 | 6 | 30 |
| Surgical_mask | 口罩 | 24 | 6 | 30 |
| toilet_paper | 卫生纸 | 24 | 6 | 30 |
| 合计 | - | 192 | 48 | 240 |

## 四、数据集构建说明
### 1. 数据采集
- 采集场景：居民区、办公场所、小区垃圾站点实景拍摄
- 采集设备：智能手机，图片统一分辨率1080P
- 采集时间：2025.10~2025.11
- 采集特点：多角度、多光照、不同完整度，丰富样本多样性

### 2. 数据标注
- 参考国标《城市生活垃圾分类标志》GB/T 19095-2019划分8个细分类别
- 双人独立标注+专人复核，标注一致性＞98%
- 单图单标签，无混合类别、无效模糊样本

### 3. 数据集划分
- 划分比例：训练:验证 = 8:2
- 分层随机抽样，各类别划分比例统一，数据分布均衡

## 五、使用说明
### 1. CSV读取
```python
import pandas as pd
train_df = pd.read_csv("labels/train_labels.csv")
val_df = pd.read_csv("labels/val_labels.csv")
2. 数据集开源说明
数据集遵循 CC0 1.0 Universal 开源协议，可免费商用、二次分发，科研使用仅需引用本项目。
六、引用格式
如使用本数据集，请引用：
孙紫阳，刘柱，王向前，李娜。面向形态多变垃圾的轻量化视觉语言模型细粒度分类数据集 [EB/OL].Github,2025,https://github.com/1583118323/Waste_FineGrained_Dataset
配套研究论文目前处于同行审稿阶段，正式见刊后将更新标准参考文献格式。
English Citation
Sun Z Y, Liu Z, Wang X Q, Li N. Fine-grained Domestic Waste Classification Dataset[EB/OL]. GitHub, 2025, https://github.com/1583118323/Waste_FineGrained_Dataset
The corresponding research paper is under peer review, formal citation will be updated after acceptance.

完整数据集压缩包下载地址：[Release v1.0](https://github.com/1583118323/Waste_FineGrained_Dataset/releases/tag/v1.0)
