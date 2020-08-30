# DGL_Chinese_Manual
This is the Chinese manual of the graph neural network library DGL, currently contains the User Guide.

Based on DGL English document：https://docs.dgl.ai/index.html

For each section, I have made a more detailed division according to the title. 
The main translation tools are Youdao Translate tools and Google Translate tools. 
When I feel that one of the translation tools is not working well, I will compare it with the other translation tool.
Due to my limited ability, there may be problems in the translation process, please point out.

Next is the relevant directory:
1.1	关于图的一些基本定义	4<br>
1.2	图、节点和边	5<br>
1.3	节点和边特征	6<br>
1.4	从外部来源创建图	7<br>
1.4.1 从外部库创建	7<br>
1.4.2 从磁盘创建	8<br>
1.5	异构图	9<br>
1.5.1	创建一个异构图	9<br>
1.5.2	处理多种类型	11<br>
1.5.3	从磁盘建立异构图	12<br>
1.5.4	边类型子图	12<br>
1.5.5	将异构图转换为同构图	13<br>
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
3.2  GDL中NN Module前向函数	20<br>
3.2.1 图检查和图类型规范化	21<br>
3.2.2 消息传递和归约	22<br>
3.2.3 归约得到输出后更新特征	22<br>
3.3	异构GraphConv模块	23<br>
3.3.1	HeteroGraphConv实现逻	23<br>
4.	图数据管道	24<br>
4.1 DGLDataset类	24<br>
4.2 下载原始数据（可选）	27<br>
4.3 处理数据	28<br>
4.3.1 处理图分类数据集	28<br>
4.3.2 处理节点分类数据集	30<br>
4.3.3 处理链接预测数据集	31<br>
4.4 保存和加载数据	33<br>
4.5 使用ogb包加载OGB数据集	34<br>
5.	训练图神经网络	35<br>
总览	35<br>
异构图	35<br>
5.1	节点分类/回归	36<br>
5.1.1 总览	37<br>
5.1.2 编写神经网络模型	37<br>
5.1.3 训练循环	37<br>
5.1.4 异构图	38<br>
5.2	边分类/回归	40<br>
5.2.1	总览	40<br>
5.2.2	模型实现和节点分类的区别	40<br>
5.2.3	训练循环	41<br>
5.2.4	异构图	42<br>
5.2.5	预测异构图上现有边的边类型	43<br>
5.3 链接预测	45<br>
5.3.1 总览	45<br>
5.3.2 与边分类模型实现的区别	45<br>
5.3.3 训练循环	45<br>
5.4	图分类	46<br>
5.4.1	总览	46<br>
5.4.2	图批量	47<br>
5.4.3	图读出	48<br>
5.4.4	编写神经网络模型	48<br>
5.4.5	训练循环	49<br>
5.4.6	异构图	50<br>
6.	大图的随机训练	51<br>
6.1	通过邻域采样训练GNN以进行节点分类	52<br>
6.1.1	定义邻域采样器和数据加载器	52<br>
6.1.2	为minibatch训练调整你的模型	53<br>
6.1.3	训练循环	53<br>
6.1.4	对于异构图	54<br>
6.2	训练利用邻域采样进行边分类的GNN	55<br>
6.2.1	定义邻域采样器和数据加载器	55<br>
6.2.2	从原始图中移除minibatch中的边以进行邻域采样	56<br>
6.2.3	调整模型以进行minibatch训练	56<br>
6.2.4	训练循环	57<br>
6.2.5	对于异构图	58<br>
6.3	通过邻域采样训练GNN进行链路预测	60<br>
6.3.1	使用负采样定义邻域采样器和数据加载器	60<br>
6.3.2	调整模型以进行minibatch训练	61<br>
6.3.3	训练循环	62<br>
6.3.4	对于异构图	62<br>
6.4	自定义领域采样器	64<br>
6.4.1	用pencil and paper进行邻域采样	65<br>
6.4.2	查找消息传递依赖项	65<br>
6.4.3	多层minibatch消息传递的双向结构	67<br>
6.4.4	块在异构图上工作	68<br>
6.4.5	实现自定义邻域采样器	69<br>
6.4.6	为异构图生成边界	71<br>
6.5	实现自定义GNN模块进行minibatch训练	71<br>
6.5.1 异构图	72<br>
6.5.2 编写可用于同构图，二部图和块的模块	74<br>
6.6 对大型图进行精确离线推断	74<br>
6.6.1 实现离线推理	75<br>
7. 分布式训练	76<br>
7.1	分布式训练的预处理	78<br>
7.1.1	负载均衡	79<br>
7.2	分布式APIs	79<br>
7.2.1	DGL分布式模块的初始化	79<br>
7.2.2	分布式图	80<br>
7.2.3	分布式张量	81<br>
7.2.4	分布式嵌入	81<br>
7.2.5 分布式采样	82<br>
7.2.6 分割工作量	83<br>
7.3	用于启动分布式训练/推理的工具	83<br>

As for the use of some APIs related to DGL, it is currently not considered.
I will further translate and organize MODEL TUTORIALS, please look forward to it.

