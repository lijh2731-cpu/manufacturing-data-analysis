# 制造业生产数据分析

## 项目简介
使用 Python 对智能工厂生产数据集（9800 条记录，17 个特征）进行完整的数据分析流程，包括数据清洗、探索性分析、可视化及统计检验。该项目展示了数据分析师在制造业场景下的常见工作流程。

## 数据来源
- 数据集：模拟智能工厂生产数据（IIoT-B2B Digital Manufacturing Dataset）
- 包含机器温度、工艺温度、转速、扭矩、刀具磨损、生产速率、设备利用率、停机时间、订单量、销售额、需求等级等字段

## 分析目标
- 探索不同需求等级下生产效率、设备利用率、停机时间的差异
- 找出与生产速率最相关的特征
- 检验需求等级对生产速率是否存在显著影响

## 主要步骤与结论

### 1. 数据清洗
- 无重复值与缺失值
- 使用箱线图 IQR 准则检测到生产速率异常值 69 个（未删除，视为真实波动）

### 2. 探索性分析
- 生产速率分布接近正态，范围约 200~800
- 按需求等级分组统计：
  - 需求等级 0：平均生产速率 498.92
  - 需求等级 1：平均生产速率 498.16
  - 需求等级 2：平均生产速率 497.41

### 3. 可视化
- 生产速率、机器利用率、停机时间随需求等级的柱状图对比
- 相关性热力图：生产速率与各特征相关性均极弱（|r|<0.02）

### 4. 统计检验
- ANOVA 方差分析结果：F = 0.159，p = 0.853
- **结论**：不同需求等级之间的生产速率无显著差异（p > 0.05）

### 5. 业务建议
- 机器利用率在高需求等级下略有下降，建议检查排产或设备维护计划
- 刀具磨损与生产速率相关性极弱，可能需要更细致的维度分析

## 技术栈
- Python 3.11
- Pandas, NumPy
- Seaborn, Matplotlib
- SciPy（ANOVA）
- Jupyter Notebook

## 文件说明
- `manufacturing_analysis.ipynb`：完整代码及运行输出
- `three_metrics_comparison.png`：三指标对比柱状图
- `correlation_heatmap.png`：特征相关性热力图
- `report.pdf`：导出的 PDF 分析报告（可选）

## 如何运行
1. 安装所需库：`pip install pandas numpy matplotlib seaborn scipy`
2. 在 Jupyter Notebook 或 VS Code 中打开 `.ipynb` 文件
3. 依次运行所有单元格

## 项目链接
[GitHub 仓库地址](https://github.com/lijh2731-cpu/manufacturing-data-analysis)

## 作者
李军豪 / GitHub: [lijh2731-cpu](https://github.com/lijh2731-cpu)
