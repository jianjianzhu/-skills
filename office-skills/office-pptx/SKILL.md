---
name: office-pptx
description: 生成、编辑、分析和验证 PowerPoint 演示文稿。适用于 PPT/PPTX、网页演示、汇报材料、动画结构和幻灯片内容规划。
metadata:
  type: skill
  source: Tabbit + Claude Code native office workflow
  tabbit_share_code: K8zbV3JgBu
---

# PPT 演示文稿

先确定受众、目的、时长、页数、素材和输出格式，再设计叙事结构。优先生成真正可编辑的 `.pptx`；需要网页演示时才输出 HTML。

## 工作流程

1. 明确主题、受众、结论和使用场景。
2. 把内容拆成开场、问题、证据、方案、行动和收束。
3. 每页只承担一个主要信息，避免把正文堆成段落。
4. 为每页选择合适的视觉元素：图表、流程、时间线、对比、图像或关键数字。
5. 生成后检查文字溢出、重叠、对比度、页边距、图表标签和占位文本。
6. 用 `markitdown` 检查内容，用 LibreOffice 转 PDF 后逐页视觉复核。
7. 对 `.pptx` 运行结构验证，修复后再交付。

## 设计原则

- 根据主题选择明确的主色、辅助色和强调色，不默认套用蓝色模板。
- 标题、正文、注释建立明显字号层级。
- 变化使用两栏、卡片、流程、数据卡、对比页和结论页，不让所有页面使用同一布局。
- 不用装饰性横条、单边色条或纯文字空白页充当设计。
- 正文左对齐，留足呼吸空间；图表保留可编辑性。

## 原生 PPTX 要求

- 新建 `.pptx` 时使用 `pptxgenjs`，并在创建第一个 slide 前设置布局。
- 所有文本框明确设置 `isTextBox: true`。
- 原生图表使用 `addChart()`，不把可用的图表渲染成图片。
- 写入后运行 `python scripts/office/validate.py output.pptx`。
- 模板编辑必须保留原有关系和资源，不能手写复制 slide XML。

## 交付格式

默认包括：`.pptx`、必要的 PDF 预览、内容大纲和验证结果。若用户只要内容，先交可直接粘贴到 PPT 的逐页结构。

来源说明：Tabbit 的 `Ultimate version PPT` 主要面向网页动画 PPT，因此这里保留其“先规划叙事、再设计视觉和交互”的优点，并改成 Claude Code 可验证的 PPTX 工作流。
