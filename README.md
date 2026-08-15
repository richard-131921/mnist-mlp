# mnist-mlp
MNIST 手写数字识别（MLP）

用 PyTorch 搭建两层多层感知机（MLP），识别 MNIST 手写数字（0-9）。
暑假自学《动手学深度学习》前四章（线性回归、softmax、多层感知机）后的练习项目。

## 模型

| 层   | 结构  |
| --- | --- |
| 展平 Flatten | 28×28 → 784 |
| 全连接 + ReLU | 784 → 256 |
| 全连接 | 256 → 10 |

约 20 万参数。

## 训练

- 数据：MNIST（6 万训练 / 1 万测试，28×28 灰度图）
- 损失：交叉熵（CrossEntropyLoss，内部含 softmax）
- 优化器：SGD，学习率 0.1，batch size 256
- 训练轮数：20

## 结果

| 模型  | 测试准确率 |
| --- | --- |
| 基础 MLP | 96.92% |
| MLP + Dropout(0.5) | 96.98% |

训练 loss 曲线、准确率曲线、模型预测可视化见 `mnist.ipynb`；
加 Dropout 的正则化对比实验见 `mnist_dropout.ipynb`。

## 怎么运行

Jupyter 打开 `mnist.ipynb` 逐格运行即可。数据集已缓存（`data/`），无需联网下载。

