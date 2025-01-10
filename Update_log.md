
# 更新日志

## 3DBubbles 0.6.0-Beta6

2024年11月29日更新

1.  使用multiprocessing实现多线程处理；

2.  优化泊松圆盘采样，增加最大迭代次数，防止参数设置不恰当陷入死循环；

3.  优化参数管理方式。

## 3DBubbles 0.5.0-Beta5

2024年11月19日更新

1.  更新FlowRenderer\_1118.py,从3DBubbles随机选取单气泡生成气泡流场，并进行四个角度的气泡点云光栅化渲染。

2.  新增3Dbubbleflowrender，提供了一个气含率为2%的三维气泡流场Demo。包括：1️⃣三维静态结构（气含率2%，mesh信息，STL格式）；2️⃣二维图像（4个角度的虚拟投影）；3️⃣全部气泡的边界框（bounding box）和类别（class）；4️⃣全部气泡的掩码（mask）信息。

## 3DBubbles 0.4.0-Beta4

2024年10月31日更新

更新重建指标（reconstruction\_index.csv）。

包括：

第1列：三维气泡文件文件名，后缀.stl。

第2列：三维结构中顶点(x,y,z)的数量。

第3列：球谐分析的级数（Degree）。

第4列：三维结构中全部顶点(x,y,z)所占字节数，坐标，以浮点数形式存储，每个坐标占4字节。

第5列：球谐分析所得球谐系数的字节数，复数形式，以npy格式存储，例如a+bj，存储为\[a,b]；。

第6列：球谐分析压缩比，定义：压缩前大小：压缩后大小。

第7列：三维点云评价指标——倒角距离（Chamfer Distance），衡量重建点云和真值点云之间最近点的平均值。

第8列：三维点云评价指标——豪斯多夫距离（Hausdorff distance），衡量重建点云和真值点云之间最近点的最大距离。

第9-10列：三维点云评价指标——Wasserstein距离，也称为推土机距离（Earth Mover’s Distance，EMD），衡量了把数据从分布p到分布q所需要移动的平均距离的最小值。

第11-13列：三维点云评价指标——F-score，是精度（Precision）和召回率（Recall）之间的调和平均值。精度计算重建点云在与真值点云一定距离内的百分比，代表重建的准确性。另一
方面，召回计算距离重建点云一定距离内真值点云的百分比，表示重建的完整性。

第14-15列：球谐分析重建后的点云围成区域的体积和表面积。

第16-19列：球谐分析重建后的点云围成区域的三维纵横比（AR\_3D），三维球体度（Sphericity\_3D），三维凸度（Convexity\_3D），三维角度度（Angularity\_3D）。

第20-25列：第14-19列参数的相对误差。

## 3DBubbles 0.3.0-beta3

2024年10月22日更新

1.  更新球谐系数。SH\_coefficient文件夹中存放10823个用于重建气泡三维结构的npy文件，重建degree从1到20。

2.  更新重建指标（reconstruction\_index.csv），包括：原始点云中点的数量和所占字节数，每个点有(x,y,z)三个点坐标，格式为float64，每个点占用3×4\=12byte；球谐重建的degree：N，从1到20，共20列。

## 3DBubbles 0.2.0-beta2

2024年10月17日更新

1.  整合同类型文件到同一个文件夹中。

2.  删除异常气泡及对应投影图像和参数。

## 3DBubbles 0.1.0-beta1

2024年10月9日更新

更新以下数据：

1.  气泡三维结构（超过10000个，mesh信息，STL格式）。

2.  二维图像（26个角度的虚拟投影）。

3.  气泡的形状参数（轴长度、等效长度、纵横比、圆度、球形度、凸度、有角指数）。