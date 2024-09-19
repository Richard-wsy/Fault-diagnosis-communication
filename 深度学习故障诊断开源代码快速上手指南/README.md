# 深度学习故障诊断开源代码快速上手指南

## 1. 数据文件准备

### 数据文件地址与格式

- 第一步是查看开源代码提供的数据文件地址和数据格式。确保数据格式和代码中要求的数据格式一致。如果数据需要预处理，参考开源代码中的预处理方法进行处理。

## 2. 配置Python库和依赖版本

### 安装依赖

- 第二步是确保Python依赖库和版本匹配。通常开源代码会提供一个 `requirements.txt` 文件，其中包含所有必要的库和版本号。
- 在代码根目录下，通过终端执行以下命令安装依赖：
  ```bash
  pip install -r requirements.txt
  ```

## 3. 配置镜像源

- 第三步，由于从国外服务器下载Python库可能速度较慢，可以配置国内镜像源。以下是常用的Python包镜像源地址：
    - 阿里云镜像源：
        ```bash
        pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
        ```
    - 清华大学镜像源：
        ```bash
        pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
        ```
    - 豆瓣镜像源：
        ```bash
       pip config set global.index-url https://pypi.doubanio.com/simple/
       ```
      
## 4. 理解代码结构

### 常见的代码文件

深度学习故障诊断领域的代码结构一般较为固定，常见的文件及其功能如下：

- **数据切片预处理.py**：用于数据的预处理、切片、数据增强等操作。
- **网络模型.py**：定义神经网络模型结构。
- **损失函数.py**：定义用于训练的损失函数。
- **plot画图.py**：负责绘制训练结果、损失曲线等图表。

### 训练文件

所有的函数和模型最后都会在 `训练train.py` 文件中进行调用和执行。

- **第四步**，理解代码的主流程，在 `训练train.py` 文件中通常包含数据加载、模型训练、结果保存等核心步骤，运行该文件启动整个训练过程。

## 5. 快速上手

获取开源代码后，快速上手的关键步骤包括：

- 确保数据格式正确，并按照代码要求进行数据准备。
- 安装所需的Python依赖库，并配置国内镜像源以加速下载。
- 理解代码的结构，尤其是数据预处理、模型定义、损失函数和绘图部分的实现逻辑。
- 运行主训练文件 `train.py`，开始模型的训练和验证。

## 6.文件目录树：directory tree
```directory tree
|-- project_root/                    # 项目根目录
|   |-- data/                        # 数据文件夹
|   |   |-- raw/                     # 原始数据
|   |   |   |-- dataset_raw.csv      
|   |   |-- processed/               # 处理后的数据
|   |       |-- dataset_processed.csv
|   |   |-- preprocess.py            # 数据预处理脚本
|
|   |-- models/                      # 模型文件夹
|   |   |-- model.py                 # 模型定义脚本
|   |   |-- loss_function.py         # 损失函数定义
|
|   |-- utils/                       # 工具函数文件夹
|   |   |-- plot.py                  # 负责绘制图像（损失曲线、结果等）
|   |   |-- data_loader.py           # 数据加载器
|   |   |-- helper_functions.py      # 辅助函数
|
|   |-- logs/                        # 日志文件夹
|   |   |-- training_logs.txt        # 训练过程中产生的日志
|
|   |-- checkpoints/                 # 模型保存的权重
|   |   |-- model_best.pth           # 最优模型权重
|   |   |-- model_latest.pth         # 最新模型权重
|
|   |-- experiments/                 # 实验结果和记录
|   |   |-- exp_1/                   # 第一个实验
|   |   |   |-- config.yaml          # 实验配置
|   |   |   |-- results.txt          # 实验结果记录
|   |   |   |-- plots/               # 实验生成的图表
|   |-- scripts/                     # 辅助脚本
|   |   |-- train.py                 # 训练主程序
|   |   |-- evaluate.py              # 评估脚本
|   |   |-- inference.py             # 推理脚本
|
|   |-- config/                      # 配置文件夹
|   |   |-- config.yaml              # 模型及训练的配置文件
|
|   |-- requirements.txt             # 依赖库文件
|   |-- README.md                    # 项目说明文档
|   |-- .gitignore                   # Git忽略文件
```

## 7.结语
- 文件目录下有我整理的几个数据集介绍
- 最后，祝大家科研顺利，希望这个开源项目能集思广益，大家一起来交流。
- 为中国的机械故障诊断领域`登峰造极`
