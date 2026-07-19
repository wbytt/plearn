# 暑假自学计划

> 目标：聚焦 Python/PyTorch + MATLAB 轻应用，跑通“AI 信号识别 + 频谱验证”小项目，产出 3 件可交付成果。

---

## 📁 最终交付物

- [ ] GitHub 仓库（含完整 Commit 记录）
- [ ] `Modulation_Recognition_PyTorch.ipynb`（1D-CNN 调制识别）
- [ ] `BER_Simulation.m` + 频谱分析脚本（MATLAB 验证）


## 🧱 第一阶段：Python 基建与 Git 习惯

### Python 数据科学三件套
- [ ] NumPy：数组创建、切片、广播、向量化运算、随机数生成
- [ ] Pandas：读取 CSV、DataFrame 索引与切片、groupby 聚合、缺失值处理
- [ ] Matplotlib / Seaborn：折线图、散点图、热力图、多子图布局
- [ ] 综合练习：用 Pandas 加载表格数据，完成 EDA（缺失值统计、相关性热力图、分布直方图）

### Git 习惯养成
- [ ] 每次代码修改后执行 `Commit` + `Push`（VS Code 图形化操作）
- [ ] 在 README.md 中记录学习进度（一句话即可）


## 🧠 第二阶段：机器学习手写实现

### 线性模型
- [ ] 手写一元线性回归（梯度下降，画出拟合直线）
- [ ] 手写逻辑回归（Sigmoid + 交叉熵损失 + 梯度下降）
- [ ] 在 `make_moons` 数据集上训练，画出决策边界

### 神经网络（NumPy 版）
- [ ] 手写 2 层神经网络（输入 → 隐藏层(ReLU) → 输出层(Softmax)）
- [ ] 手写反向传播（链式求导，矩阵维度对齐）
- [ ] 在 `iris` 或 `make_moons` 上训练，验证 loss 下降

### 数据持久化
- [ ] 将训练好的模型权重保存为 `.npy` 文件


## ⚙️ 第三阶段：PyTorch 深度学习实战

### PyTorch 入门
- [ ] Tensor 创建与操作、Autograd 自动求导、`nn.Module` 继承
- [ ] 用 PyTorch 重写第二阶段的 2 层神经网络

### 核心项目：RML2016.10a 调制识别
- [ ] 下载 RML2016.10a 数据集
- [ ] 了解数据格式：[样本数, 2, 128]（I/Q 两路，128 个时间步）
- [ ] 搭建 1D-CNN 模型（Conv1d → ReLU → MaxPool → Linear）
- [ ] 划分训练集/测试集，编写 DataLoader
- [ ] 训练 10-20 个 epoch，记录 train_loss / test_acc
- [ ] 绘制训练曲线（loss 下降图、准确率曲线）
- [ ] 绘制混淆矩阵
- [ ] 保存模型权重 `.pth` 文件
- [ ] 选取几个预测错误的样本，保存其信号数据


## 📡 第四阶段：MATLAB 信号验证

> 若无 MATLAB，可用 Octave 或 Python `scipy.signal` 替代。

### MATLAB 基础
- [ ] 学会 MATLAB 矩阵操作、`.m` 脚本编写、`plot` 绘图
- [ ] 加载 `.mat` 文件

### 信号生成与仿真
- [ ] 编写 MATLAB 脚本：生成单频正弦波 + 高斯白噪声
- [ ] 绘制时域波形和频谱图（FFT）
- [ ] 跑通 QPSK 调制/解调流程，绘制 BER 曲线

### AI + 通信交叉分析
- [ ] 加载第三阶段保存的预测错误样本（.mat 格式）
- [ ] 在 MATLAB 中绘制这些样本的时域/频域图
- [ ] 添加注释，分析可能的原因


## 🧰 工具清单

| 工具 | 用途 |
| :--- | :--- |
| VS Code | 主编辑器（含 Python + Jupyter 插件） |
| Anaconda | Python 环境管理 |
| GitHub Desktop | Git 图形化界面 |
| Jupyter Notebook | 代码实验与记录（在 VS Code 中打开） |
| MATLAB | 信号处理验证（或用 Octave 替代） |


## 🛡️ 容错原则

- **单个 Bug 调试超过 1.5 小时** → 记录问题 → 暂时跳过
- **环境配置超过 2 小时未解决** → 换替代方案（Octave / scipy.signal）
- **核心底线**：跑通调制识别项目即算成功，其余皆可取舍