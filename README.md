# 2021-07-13补充

2020年9月，DGL社区的一群热心贡献者把DGL用户指南译成了中文，方便广大中文用户群学习和使用DGL，这里贴下他们的地址:<br>
<a href="https://docs.dgl.ai/en/0.6.x/api/python/">https://docs.dgl.ai/en/0.6.x/api/python/</a>

# DGL_Chinese_Manual（DGL中文文档）
This is the Chinese manual of the graph neural network library DGL, contains the User Guide and Model Tutorials.

Based on DGL English document：https://docs.dgl.ai/index.html

## Written in the front
I uploaded the word version and the pdf version at the same time, you can use it at will. 
But I hope you can point out the source when you use it. 
After all, translation is not easy (although I use a translation tool...).

## User Guide

For each section, I have made a more detailed division according to the title. 
The main translation tools are Youdao Translate tools and Google Translate tools. 
When I feel that one of the translation tools is not working well, I will compare it with the other translation tool.
Due to my limited ability, there may be problems in the translation process, please point out.

Next is the relevant directory:<br>
目录<br>
begin 安装	4<br>
使用conda安装	4<br>
使用pip安装	4<br>
使用源安装	4<br>
设置默认的Backend	4<br>
1.	图	4<br>
  1.1	关于图的一些基本定义	4<br>
  1.2	图、节点和边	5<br>
  1.3	节点和边特征	6<br>
  1.4	从外部来源创建图	7<br>
      ---1.4.1 从外部库创建	7<br>
      ---1.4.2 从磁盘创建	8<br>
  1.5	异构图	9<br>
      ---1.5.1	创建一个异构图	9<br>
      ---1.5.2	处理多种类型	11<br>
      ---1.5.3	从磁盘建立异构图	12<br>
      ---1.5.4	边类型子图	12<br>
      ---1.5.5	将异构图转换为同构图	13<br>
  1.6 在GPU上使用DGLGraph	14<br>
2.	消息传递	15<br>
  2.1	消息传递案例	15<br>
  2.2	内置功函数和消息传递APIs	15<br>
  2.3	编写有效的消息传递代码	17<br>
  2.4	在图的一部分上应用消息传递	18<br>
  2.5	在消息传递中使用边权重	18<br>
  2.6	在异构图中的消息传递	18<br>
3.	建立GNN模块	19<br>
  3.1	DGL中NN Module的构造函数	19<br>
  3.2   GDL中NN Module前向函数	20<br>
      ---3.2.1 图检查和图类型规范化	21<br>
      ---3.2.2 消息传递和归约	22<br>
      ---3.2.3 归约得到输出后更新特征	22<br>
  3.3	异构GraphConv模块	23<br>
      ---3.3.1	HeteroGraphConv实现逻	23<br>
4.	图数据管道	24<br>
  4.1   DGLDataset类	24<br>
  4.2   下载原始数据（可选）	27<br>
  4.3   处理数据	28<br>
      ---4.3.1 处理图分类数据集	28<br>
      ---4.3.2 处理节点分类数据集	30<br>
      ---4.3.3 处理链接预测数据集	31<br>
  4.4   保存和加载数据	33<br>
  4.5   使用ogb包加载OGB数据集	34<br>
5.	训练图神经网络	35<br>
总览	35<br>
异构图	35<br>
  5.1	节点分类/回归	36<br>
      ---5.1.1 总览	37<br>
      ---5.1.2 编写神经网络模型	37<br>
      ---5.1.3 训练循环	37<br>
      ---5.1.4 异构图	38<br>
  5.2	边分类/回归	40<br>
      ---5.2.1	总览	40<br>
      ---5.2.2	模型实现和节点分类的区别	40<br>
      ---5.2.3	训练循环	41<br>
      ---5.2.4	异构图	42<br>
      ---5.2.5	预测异构图上现有边的边类型	43<br>
  5.3   链接预测	45<br>
      ---5.3.1 总览	45<br>
      ---5.3.2 与边分类模型实现的区别	45<br>
      ---5.3.3 训练循环	45<br>
  5.4	图分类	46<br>
      ---5.4.1	总览	46<br>
      ---5.4.2	图批量	47<br>
      ---5.4.3	图读出	48<br>
      ---5.4.4	编写神经网络模型	48<br>
      ---5.4.5	训练循环	49<br>
      ---5.4.6	异构图	50<br>
6.	大图的随机训练	51<br>
  6.1	通过邻域采样训练GNN以进行节点分类	52<br>
      ---6.1.1	定义邻域采样器和数据加载器	52<br>
      ---6.1.2	为minibatch训练调整你的模型	53<br>
      ---6.1.3	训练循环	53<br>
      ---6.1.4	对于异构图	54<br>
  6.2	训练利用邻域采样进行边分类的GNN	55<br>
      ---6.2.1	定义邻域采样器和数据加载器	55<br>
      ---6.2.2	从原始图中移除minibatch中的边以进行邻域采样	56<br>
      ---6.2.3	调整模型以进行minibatch训练	56<br>
      ---6.2.4	训练循环	57<br>
      ---6.2.5	对于异构图	58<br>
  6.3	通过邻域采样训练GNN进行链路预测	60<br>
      ---6.3.1	使用负采样定义邻域采样器和数据加载器	60<br>
      ---6.3.2	调整模型以进行minibatch训练	61<br>
      ---6.3.3	训练循环	62<br>
      ---6.3.4	对于异构图	62<br>
  6.4	自定义领域采样器	64<br>
      ---6.4.1	用pencil and paper进行邻域采样	65<br>
      ---6.4.2	查找消息传递依赖项	65<br>
      ---6.4.3	多层minibatch消息传递的双向结构	67<br>
      ---6.4.4	块在异构图上工作	68<br>
      ---6.4.5	实现自定义邻域采样器	69<br>
      ---6.4.6	为异构图生成边界	71<br>
  6.5	实现自定义GNN模块进行minibatch训练	71<br>
      ---6.5.1 异构图	72<br>
      ---6.5.2 编写可用于同构图，二部图和块的模块	74<br>
  6.6 对大型图进行精确离线推断	74<br>
      ---6.6.1 实现离线推理	75<br>
7. 分布式训练	76<br>
  7.1	分布式训练的预处理	78<br>
      ---7.1.1	负载均衡	79<br>
  7.2	分布式APIs	79<br>
      ---7.2.1	DGL分布式模块的初始化	79<br>
      ---7.2.2	分布式图	80<br>
      ---7.2.3	分布式张量	81<br>
      ---7.2.4	分布式嵌入	81<br>
      ---7.2.5 分布式采样	82<br>
      ---7.2.6 分割工作量	83<br>
  7.3	用于启动分布式训练/推理的工具	83<br>
  
## Model Tutorials

I have completed the translation of Model Tutorials.Since many pictures in the official documents are invalid, 
so I marked the invalid places. In this document, you will find that in some places I directly use the original English text, 
because the meaning of the original sentence may be clearer. Since I am a bit lazy, I will directly use <br>
https://blog.csdn.net/weixin_45613751/ <br>
to take screenshots of some complex formulas.

Next is the relevant directory:<br>
目录<br>
1.	总览	2<br>
--1.1 神经网络和它的变体	2<br>
--1.2 批处理很多小图	2<br>
--1.3 生成模型	2<br>
--1.4 从图角度重新审视经典模型	3<br>
2.	图卷积网络	3<br>
--2.1 模型总览	3<br>
----2.1.1 从消息传递的角度看GCN	3<br>
----2.1.2 用DGL实现GCN	3<br>
----2.1.3 GCN中的公式	8<br>
--2.2 关系图卷积网络	8<br>
----2.2.1 R-GCN简介	9<br>
----2.2.2 R-GCN的关键思想	9<br>
----2.2.3 在DGL中实现R-GCN	10<br>
----2.2.4 第二项任务：链接预测	16<br>
3.	线性图神经网络	16<br>
--3.1 使用Cora数据集进行监督的社区检测任务	17<br>
----3.1.1 社区检测	17<br>
----3.1.2 Cora数据集	17<br>
----3.1.3 来自Cora的二元社区子图和测试数据集	18<br>
----3.1.4 在有监督的环境中进行社区检测	19<br>
--3.2 线性图神经网络的关键思想	20<br>
----3.2.1 什么是线性图？	20<br>
----3.2.2 LGNN中的一层，算法结构	20<br>
--3.3 在DGL中实现LGNN	21<br>
----3.3.1 实现prev和deg作为张量操作	22<br>
----3.3.2 在DGL中将radiusradius实现为消息传递	22<br>
----3.3.3 实现fuse为稀疏矩阵乘法实	22<br>
----3.3.4 完成f(x, y)	23<br>
----3.3.5 将LGNN抽象链接为LGNN层	24<br>
----3.3.6 链接LGNN层	24<br>
--3.4 训练与推断	25<br>
--3.5 可视化训练进程	26<br>
--3.6 批处理并行图	27<br>
4.	图注意力网络	28<br>
--4.1 将注意力引入到GCN	28<br>
--4.2 在DGL中的GAT	30<br>
----4.2.1 公式（1）	31<br>
----4.2.2 公式（2）	31<br>
----4.2.3 公式（3）和（4）	32<br>
----4.2.4 多头注意力	32<br>
----4.2.5 将所有放在一起	33<br>
--4.3 可视化和理解所学注意力	36<br>
--4.4 蛋白质相互作用（PPI）网络	38<br>
--4.5 下一个是什么？	41<br>
5.	DGL中的Tree-LSTM	41<br>
--5.1 任务和数据集	41<br>
--5.2 步骤1：批量化	43<br>
--5.3 步骤2：具有消息传递API的Tree-LSTM单元	44<br>
--5.4 步骤3：定义遍历	45<br>
--5.5 把它们放在一起	47<br>
--5.6 主循环	48<br>
6.	图生成模型	50<br>
--6.1 介绍	51<br>
--6.2 DGMG：主要流程	51<br>
--6.3 DGMG：优化目标	53<br>
--6.4 GMG：实现	54<br>
----6.4.1 DGMG类	54<br>
----6.4.2 编码动态图	55<br>
----6.4.3 动作	58<br>
----6.4.4 将它们放在一起	62<br>
7.	胶囊网络	65<br>
--7.1 胶囊的主要思想	65<br>
--7.2 模型实现	65<br>
----7.2.1 步骤1：设定和图初始化	65<br>
----7.2.2 步骤2：定义消息传递功能	66<br>
----7.2.3 步骤3：测试	67<br>
8.	Transformer	69<br>
--8.1 Transformer中的注意力层	70<br>
--8.2 多头注意力机制	70<br>
--8.3 DGL如何通过图神经网络实现Transformer	71<br>
----8.3.1 图结构	71<br>
----8.3.2 消息传递	71<br>
----8.3.3 预处理和后处理	74<br>
--8.4 Transformer graph的主要类	75<br>
--8.5 训练	77<br>
----8.5.1 任务和数据集	77<br>
----8.5.2 构造图	78<br>
--8.6 将它们放在一起	79<br>
--8.7 可视化	80<br>
----8.7.1 多头注意力	81<br>
8.8	自适应通用Transformer	81<br>

You can also find some other Chinese materials in the following places:<br>
<a href="https://blog.csdn.net/weixin_45613751/">https://blog.csdn.net/weixin_45613751/</a><br>
<a href="https://www.yuque.com/mamudechengxuyuan/od99k2/in0pv9">https://www.yuque.com/mamudechengxuyuan/od99k2/in0pv9</a><br>





