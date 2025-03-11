# DeepARG: DeepARG: An Explainable Machine Learning-based Intelligent System for Microbial Resistance Gene Identification

![DeepARG Workflow](src/figure/figure.png)

## 📖 项目简介
DeepARG是基于深度学习的微生物抗性基因识别系统，创新性地解决了以下行业痛点：
- **传统方法依赖实验验证**：湿实验验证周期长（3-6个月/基因）
- **现有算法可解释性差**：无法追溯预测结果的生物学依据
- **多平台兼容性差**：缺乏统一的分析工作流

技术亮点：

1. 🧠 基于TensorFlow构建深度神经网络模型
2. ⚙️ 采用Snakemake构建标准化分析流程
3. 🎯二次筛选候选结果

## 🛠️ 技术架构
![Tech Stack](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.6-orange)
![SHAP](https://img.shields.io/badge/SHAP-0.41.0-red)
![Bioconda](https://img.shields.io/badge/Bioconda-DeepGOPlus-green)

核心技术组件：
| 模块                | 技术实现                     |
| ------------------- | ---------------------------- |
| 工作流管理          | Snakemake DAG引擎            |
| 深度学习（CNN）预测 | Tensorflow架构               |
| GO注释              | DeepGOPlus(卷积神经网络注释) |
| 序列处理            | SeqKit高效处理               |
|                     |                              |
|                     |                              |



## 🚀 快速安装

### 前置要求
- Miniconda3 (Python ≥3.8)
- Linux/macOS系统
- 推荐配置：32GB内存 + NVIDIA GPU (CUDA 11.x)

### 环境部署
```bash
# 克隆仓库
git clone https://github.com/XT33KAKA/DeepARG.git
cd DeepARG

# 创建Conda环境
conda env create -f environment.yml

# 激活环境
conda activate DeepARG

# 安装核心脚本到系统路径
sudo cp src/work_script/* /usr/local/bin/

# 安装snakemake
pip install snakemake==7.22
```

## 📈 使用指南

### 标准分析流程

```bash
# 进入环境
conda activate DeepARG_env

#使用流程
snakemake -s workflow -c {线程数} -p --use-conda 

```

## 📂 目录结构

```bash
DeepARG/
├── config/              # 配置文件
├── model/               # 模型存储
├── result/              # 输出结果
├── src/
│   ├── figure/          # 流程示意图
│   └── work_script/     # 核心执行脚本
└── environment.yml      # 依赖环境
```

