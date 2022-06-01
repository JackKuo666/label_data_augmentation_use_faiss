# 基于 simbert chinese 的 从无监督数据向有标签数据扩增项目

## 依赖
```py
python 3.7
bert4keras 0.11.3
faiss-gpu 1.7.2
yaml 6.0
conda install mkl-service # mkl只能这样索引
```

## 原理

根据带标签数据集label_query_path和无标签数据集unlabel_query_path来enlarge数据集

先根据unlabel_query_path构建索引

然后找label_query_path相似文本存储到enlarge_data_path，数据格式为['sim_text', 'sim_value', 'label']

用到的index 是faiss 

## 运行

```py
python data_augmentation.py
```