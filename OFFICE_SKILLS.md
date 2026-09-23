# 办公与研究技能包

这是为 Claude Code 整理的办公文档与研究技能集合，来源包括 Tabbit 技能广场中可公开审查的条目，以及本机已有的原生文档处理工作流。

## 已包含技能

| 技能 | 用途 | 主要输出 |
|---|---|---|
| [office-pptx](office-skills/office-pptx/SKILL.md) | 演示文稿规划、生成、编辑、验证 | PPTX、PDF 预览、逐页大纲 |
| [office-xlsx](office-skills/office-xlsx/SKILL.md) | Excel 建模、公式、台账、数据分析 | XLSX、公式说明、校验结果 |
| [office-pdf](office-skills/office-pdf/SKILL.md) | PDF 创建、提取、合并、拆分、OCR | PDF、文本/表格、OCR 结果 |
| [office-docx](office-skills/office-docx/SKILL.md) | Word 报告、合同、模板和目录 | DOCX、PDF 预览 |
| [office-report](office-skills/office-report/SKILL.md) | 正式报告、周报、事实核查、RFP | Markdown、DOCX、PDF、PPTX |
| [multimodal-document-analysis](office-skills/multimodal-document-analysis/SKILL.md) | 图片、扫描件、合同、表格和图表分析 | 结构化分析、XLSX/CSV |
| [fact-checking](office-skills/fact-checking/SKILL.md) | 事实、新闻和技术主张核验 | 证据报告、来源清单 |
| [cfo-strategy](office-skills/cfo-strategy/SKILL.md) | 预算、FP&A、现金流、资本配置 | 财务分析、情景模型 |
| [product-analysis](office-skills/product-analysis/SKILL.md) | 产品、竞品、技术和商业化分析 | 竞品报告、对比表 |
| [ai-weekly-report](office-skills/ai-weekly-report/SKILL.md) | AI 模型、研究、行业和工具周报 | 中文 Markdown 周报 |
| [deploy-guide](office-skills/deploy-guide/SKILL.md) | GitHub 项目和服务部署指南 | Compose、命令、健康检查 |
| [ai-news-daily](office-skills/ai-news-daily/SKILL.md) | AI 新闻日报 | Markdown 日报 |

## 与本地已有能力的关系

- `office-pptx` 使用本机的 `pptxgenjs`、LibreOffice、`markitdown` 和结构验证流程。
- `office-xlsx` 使用 `openpyxl`、`pandas`、LibreOffice 公式重算和错误检查。
- `office-pdf` 使用 `pypdf`、`pdfplumber`、`reportlab`、OCR 和 Poppler。
- `office-docx` 使用 `docx`、`pandoc`、LibreOffice 和 XML 级编辑。
- `multimodal-document-analysis` 可以和已有 `pdf-ocr-auto` 联动处理扫描合同和图片材料。

## Tabbit 来源与取舍

本次读取了 Tabbit 技能广场公开分页，共 358 个条目。纳入并改造的主要来源：

- `Ultimate version PPT` — `K8zbV3JgBu`
- `Data Analyst` — `LSwSWV6J1G`
- `Data Analysis` — `NQUdgx5cG4`
- `Multimodal Analyst` — `a6PYSdbGAx`
- `Analysis Everything Product Analysis` — `TUGiDcUoF6`
- `Fact-checking` — `Ukjtmiq9Rc`
- `CFO / Financial Strategy` — `UQs6umRgJE`
- `AI Information Weekly` — `24jmpjLjfy`
- `RFP Generator` — `LefLKTmYuX`
- `GitHub Project Deployment Guide 2.0` — `UrQpS6fMDd`

Tabbit 中没有找到可公开审查、且明确适合 Claude Code 的独立 Excel/PDF/Word 生成技能。因此这三类采用本机可验证的原生工作流，而不是导入不相关或依赖 Tabbit 页面环境的条目。

## 安全取舍

未纳入：

- GitHub 凭据搜集/Secret Dorking 技能
- 需要 Tabbit 专有页面、桌宠、主页注入或会话管理的脚本
- 会自动向外部平台发布内容的技能
- 正文被隐藏、权限受限、无法审查的运行时技能
- 会把真实密码、Token 或私钥写入文档的流程

## 使用示例

```text
用 office-pptx 把这份研究报告做成 10 页汇报 PPT，先给逐页大纲，再生成 PPTX 并做视觉检查。
```

```text
用 office-xlsx 把这份结算数据整理成可复核的台账，保留公式、来源和假设，最后重算并检查公式错误。
```

```text
用 office-report + office-docx 把这些资料整理成正式审查报告，并输出 DOCX 和 PDF 预览。
```

```text
用 multimodal-document-analysis 读取这份扫描合同，提取表格和关键条款，标出低置信度内容。
```

## 目录说明

本仓库只提交可复用技能和说明，不提交用户合同、扫描图片、临时 OCR 文件、凭据或本机缓存。
