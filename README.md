# AI_Bioinformatic
Agent skill for Bioinformatic 

**Skill1: geo-search**
输入想要检索的信息（如成人GBM的单细胞测序数据、队列表达数据RNAseq/基因芯片）， AI agent会在GEO等公共数据库 AI四轮web_search，并剔除不符合需求的，最后汇总整理成Excel表格

**Skill2: scrna-cell-annotation**
输入不同cluster的dotplot、findmarker、Umap空间信息,AI agent结合cell marker数据库、AI存储信息和Pubmed数据库，进行辅助打分和AI推理，判断每个cluster的细胞注释。
