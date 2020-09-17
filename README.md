# To-do List Classification

传统机器学习要求传入的训练集组建的BOW模型足够大，若待测语句元素不存在于生成的BOW模型中，预测精度会大幅下降。对于本项目中指令类短文本的预测精度影响尤为显著。

```word2vec：```自我扩充，泛化传入的训练集语料，可以识别近义语料。

    本文主要记录笔者在完成训练过程中遇到的小tip，比较规范的内容可以参考其他许多大佬们的博客文章。

## 训练词向量
- 标注语料
- pd.read_csv()读入
- jieba分词，以list格式保存每篇文章的分词结果
- 调用```gensim.model```中```Word2Vec```方法创建实例化对象，训练得到各个词向量模型
- 保存模型

## 获取文章词向量
- 获取文章中每个词的词向量

    ```vector_list = [word2vec.model.wv[k] for k in wordlist if k in word2vec_model]```
- 获取语料向量（词向量均值）
- 转换为矩阵

## 标签编码转换为矩阵

- 调用```sklearn.preprocessing```的```LabelEncoder```方法

    ```label = LabekEncoder()```
    
    ```y = label.fit_transform(data['分类']```

## 拆分X，y为训练集/测试集

## 传入训练模型（Logistics Regression，Random Forest，SVM，etc）并评估
