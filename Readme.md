# 暑假自学计划

> 目标：从 Python 数据科学 -> 手写 ML -> PyTorch 深度学习 -> 信号调制识别
> 通信工程（大二），以手写实现理解原理，以 RML2016.10a 项目串联全流程

---

## 最终交付物

- [ ] GitHub 仓库（含完整 Commit 记录）
- [ ] handwritten_ml.ipynb（手写线性回归 / 逻辑回归 / 2 层 NN）
- [ ] Modulation_Recognition_PyTorch.ipynb（加深版 1D-CNN 调制识别 + SNR 分析）
- [ ] error_analysis.ipynb（错误样本可视化分析）


## 第一阶段：Python 基建与 Git 习惯（已完成）

### Python 数据科学三件套
- [x] NumPy：数组创建、切片、广播、向量化运算、随机数生成
- [x] Pandas：读取 CSV、DataFrame 索引与切片、groupby 聚合、缺失值处理
- [x] Matplotlib / Seaborn：折线图、散点图、热力图、多子图布局
- [x] 综合练习：用 Pandas 加载表格数据，完成 EDA

### Git 习惯养成
- [x] 每次代码修改后执行 Commit + Push
- [x] 在 README.md 中记录学习进度


## 第二阶段：机器学习手写实现

设计思路：手写所有核心算法，理解梯度下降、前向/反向传播的本质。最后用 sklearn 验证手写结果。

### 线性模型
- [ ] 手写一元线性回归（梯度下降，画出拟合直线）
- [ ] 手写逻辑回归（Sigmoid + 交叉熵损失 + 梯度下降，画出决策边界）
- [ ] 桥接思考：写完逻辑回归后，手动对比它和单层神经网络的关系

### 神经网络（NumPy 版）
- [ ] 手写 2 层神经网络（输入 -> 隐藏层 ReLU -> 输出层 Softmax）
- [ ] 手写反向传播（链式求导，矩阵维度对齐）
- [ ] 在 iris 或 make_moons 上训练，验证 loss 下降，画出决策边界

### 数据持久化与 sklearn 验证
- [ ] 将训练好的模型权重保存为 .npy 文件
- [ ] 用 sklearn 的同类模型在手写数据上跑一遍，对比结果


## 第三阶段：PyTorch 深度学习实战

### PyTorch 入门
- [ ] Tensor 创建与操作、Autograd、nn.Module
- [ ] 理解 PyTorch 训练范式：Dataset -> DataLoader -> optimizer.zero_grad() -> loss.backward() -> optimizer.step()
- [ ] 用 PyTorch 重写第二阶段的两层网络
- [ ] （可选）用 MNIST 跑通完整训练-评估流程，巩固范式

### 核心项目：RML2016.10a 调制识别
- [ ] 下载 RML2016.10a 数据集，了解数据格式 [样本数, 2, 128]
- [ ] 搭建加深版 1D-CNN（示例：Conv1d -> ReLU -> Conv1d -> ReLU -> MaxPool -> Dropout -> Linear -> Linear）
- [ ] 划分训练集/测试集，编写 DataLoader
- [ ] 训练 10-20 个 epoch，记录 train_loss / test_acc
- [ ] 绘制训练曲线（loss 下降图、准确率曲线）
- [ ] 按信噪比（SNR）分组评估，绘制 accuracy vs SNR 曲线
- [ ] 绘制混淆矩阵
- [ ] 保存模型权重 .pth 文件
- [ ] 选取预测错误的样本，保存 I/Q 数据
- [ ] 容错：若基线准确率低于 50%，尝试增加层数 / 加 Dropout / 调学习率


## 第四阶段：错误样本分析与信号可视化（Python 版）

设计思路：不用 MATLAB。用 Python 的 scipy.signal + matplotlib 完成同样的交叉分析目标。

- [ ] 加载第三阶段保存的预测错误样本
- [ ] 绘制时域波形图（I/Q 两路）
- [ ] 绘制频谱图（FFT，scipy.signal）
- [ ] 添加注释，分析可能的混淆原因
- [ ] （可选）用 scipy.signal 生成简单合成信号，验证低 SNR 下的识别难度


## 工具清单

| 工具 | 用途 |
| :--- | :--- |
| VS Code | 主编辑器（含 Python + Jupyter 插件） |
| Anaconda | Python 环境管理 |
| GitHub Desktop | Git 图形化界面 |
| Jupyter Notebook | 代码实验与记录 |
| scipy.signal | 第四阶段信号分析辅助 |


## 容错原则

- 单个 Bug 调试超过 1.5 小时 -> 记录问题 -> 暂时跳过
- 环境配置超过 2 小时未解决 -> 换替代方案
- 模型效果不达预期 -> 按第三阶段容错步骤调优
- 核心底线：跑通调制识别项目 + 错误样本分析即算成功
- 第四阶段如时间不够，可只做加载错误样本画时域图这一项
