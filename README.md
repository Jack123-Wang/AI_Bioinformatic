# AI_Bioinformatic

基于 Claude 的生物信息学 Agent Skill 合集。

---

## Skill 1: geo-search

输入想要检索的信息（如 GBM 的单细胞测序数据、队列表达数据 RNAseq/基因芯片），AI Agent 会在 GEO、TCGA/GDC、CGGA、CellxGene、ArrayExpress、SRA 等公共数据库进行四轮 web_search，并通过文献驱动的第四轮检索发现预定义列表之外的新数据库。检索完成后剔除不符合需求的数据集，最终汇总整理成 Excel 表格。

**使用方式：** 告诉 Claude 你的研究主题、物种、数据类型和质控要求，Claude 会逐步收集信息后开始检索。

**输出：** `GEO_search_[主题]_[日期].xlsx`，包含合格数据集、不合格数据集、检索日志及新发现数据库。

---

## Skill 2: scrna-annotation

输入不同 cluster 的 DotPlot 表达矩阵、FindMarkers 差异基因和 UMAP 空间距离信息，AI Agent 结合 CellMarker/PanglaoDB 离线数据库、AI 存储知识和 PubMed 文献构建 marker 知识库，对每个 cluster 进行多维证据整合与 AI 推理，判断细胞类型并给出置信度和编号推理依据。完成注释后生成 Excel 报告，并输出 cluster 级别和 celltype_AI 级别的可视化 R 代码（DotPlot + DimPlot）。

**使用方式：** 提供 Seurat 对象，Claude 生成导出三张输入表的 R 代码，用户运行后上传，Claude 开始逐 cluster 注释。

**输出：** `scRNA_annotation_[样本]_[日期].xlsx` + cluster 和 celltype_AI 可视化 R 代码。

---

## 使用方法

本合集 skill 适用于 [Claude.ai](https://claude.ai)，将 `.skill` 文件上传至 Claude skill 目录（`/mnt/skills/user/`）即可使用。
