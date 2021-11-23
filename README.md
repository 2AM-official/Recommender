# Recommender

This is the assignment 2 of CSE 258 Web Mining and Recommender Systems.

Dataset: https://www.kaggle.com/stefanoleone992/imdb-extensive-dataset?select=IMDb+movies.csv

Initial Model:



Mile Stones:

11.22 -- 基础的数据清洗和特征向量提取

1. 构造了genre的one-hot
2. 在country中选了拍摄最多的10个国家，构造one-hot
3. 构造了以director的one-hot

遇到的问题：

1. 如何更有效率地展示director的特征，一共有2w多个导演，怎样选择构建导演的feature：
    - 若根据评分，有可能出现只导过一个电影获得高分的
    - *目前想到可以用参与投票的用户数来进行*
2. 演员同上，不知道如何更好地展示feature
3. 如何根据时间构造one-hot，因为每个年份和时间段排的电影数量不同

需要注意的：

1. 数据中在演员或其他string的部分有可能出现nan导致无法用split读取和分割。
2. 演员的名字可能出现'Al Pacino'（分割完第一个不是空格）和' Al Pacino'（分割完第一个字符是空格）两种，我和薛哥采用的是直接把空格都删到变成'AlPacino'这样的输出。
3. 数据有可能和实际IMDB有差别，我们搜索到的一个电影评分和实际IMDB评分不同。