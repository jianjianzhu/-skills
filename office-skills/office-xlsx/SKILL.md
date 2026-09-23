---
name: office-xlsx
description: 生成、编辑、分析和验证 Excel 工作簿。适用于 XLSX、报表、预算、成本测算、台账、数据清洗、公式和图表。
metadata:
  type: skill
  source: Claude Code native office workflow + Tabbit data analysis skills
  tabbit_share_codes: LSwSWV6J1G,NQUdgx5cG4,UQs6umRgJE
---

# Excel 工作簿

优先使用 `openpyxl` 创建和编辑 `.xlsx`，使用 `pandas` 做批量数据处理。先确认原文件的 sheet、输入区域、公式、样式和外部引用，不覆盖用户已有公式或宏。

## 工作流程

1. 明确目标、表名、列名、输入输出范围和计算口径。
2. 读取并检查数据粒度、缺失值、重复值、异常值和数据日期。
3. 先写少量公式并核对引用关系，再扩展到完整网格。
4. 使用公式而不是把计算结果硬编码到单元格。
5. 为假设、来源和硬编码数字增加可见注释或说明区域。
6. 使用专业字体、清晰数字格式、冻结窗格、筛选和合理列宽。
7. 公式工作簿必须运行 `python scripts/recalc.py output.xlsx`。
8. 用 `markitdown` 和 `data_only=True` 复核公式结果及表格内容。

## 公式纪律

- 优先使用 `SUMIFS`、`INDEX`、`MATCH`、`IFERROR`、`SUMPRODUCT`。
- 不使用 LibreOffice 无法稳定计算的 `XLOOKUP`、`FILTER`、`UNIQUE`、`SORT`、`SEQUENCE`。
- 百分比保存为小数，负数使用括号，零值使用短横线。
- 避免外部工作簿链接；如原文件存在外部引用，保存前先明确风险。
- `.xlsm` 必须使用 `keep_vba=True`。

## 分析输出

数据分析遵循：问题界定 → 数据质量 → 总体与分组趋势 → 异常 → 驱动因素 → 风险与限制 → 建议。明确区分相关性与因果性、统计显著性与业务重要性。

## 交付格式

默认包括：`.xlsx`、字段/公式说明、数据来源与假设、验证结果。若用户需要图表，优先使用 Excel 原生图表而非截图。
