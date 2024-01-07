# RUC_basicprogramming_0107项目简介
这是编程基础期末大作业，选题是机器学习方法进行球队胜负关系预测。代码中用了逻辑斯蒂回归和决策树两种模型对两支球队的比赛胜负进行预测。数据集来源于NBA数据官方网站https://www.basketball-reference.com/

采用某一赛季29支球队之间的比赛结果以及球队各项指标，例如二分球命中率、失误数等构建数据集。
# 复现说明
python3.7

matplotlib 3.5.3

sklearn 0.19.2

statsmodels 0.13.5

numpy 1.19.5

pandas 1.1.5

“WL.txt”文件是球队之间交手的比赛结果，“2002-2003team.txt”是球队的各项数据，以上两项用于构建数据集；

“2002-2003Rk.txt”是球队最终排名，“DET.txt”是底特律活塞队的数据，用以结果分析。

依次执行ipynb文件中的代码即可。
# 代码构建
函数man_data(X1, X2)用来数据预处理。“WL.txt”表中记载了某两支球队的名称以及237场比赛的最终分数情况。“2002-2003team.txt”表记录了每支球队的各项数据。需要根据胜负记录中的两支球队，在“2002-2003team.txt”表中找到对应两支球队，将两支球队各项指标作差得到自变量的数据。analyse_res (pre, game_res, Rk)是对预测结果进行分析的函数，找出预测错误的球队实际的“战力”排名以分析是否为“爆冷”局。

在建立两种模型进行预测时，由于两种模型进行训练、预测等的步骤大致相似，因此建立一个基类BaseClassifier，属性包括所使用的模型和模型参数，成员函数包括模型训练、预测、分析、交叉验证以及参数寻优。而派生的两个类LogisticRegressionClassifier和DecisionTreeClassifierWrapper分别定义了逻辑斯蒂回归模型和决策树模型，此外DecisionTreeClassifierWrapper类里还对基类中的参数寻优函数进行了重写。

在主函数中进行类声明、画图等。

