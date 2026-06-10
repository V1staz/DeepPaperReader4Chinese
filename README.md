# Paper Reader

[English](README_EN.md) | **中文**

面向 Codex 的学术论文阅读技能。给定一篇 PDF 论文后，既可以生成中文译述式精读笔记和研究级中文分析，也可以按快速报告模式生成单文件中文速读报告。重点是重构作者推理、拆解方法机制、分析实验信号、暴露潜在弱点，并推导后续研究方向。

本仓库同时保留旧版 Claude Code 单文件用法：

- `SKILL.md`：Codex 标准技能入口。
- `paper-reader.md`：兼容旧版 Claude Code 的单文件技能。
- `agents/openai.yaml`：Codex UI 元数据。

## 生成文件

完整模式生成：

1. `<论文名>_translation.md`：中文译述式精读笔记，保留章节结构、作者论证逻辑、核心算法、关键技术细节、主要实验发现和公式，但不逐字翻译。
2. `<论文名>_analysis.md`：研究级中文分析，覆盖任务定义、核心挑战、洞察与创新、方法拆解、实验分析、潜在弱点、未来方向、第一性原理重构、文献定位和研究者要点。

快速报告模式生成：

1. `<论文名>_fastreport.md`：单文件中文速读报告，覆盖任务定义、实际方法细节（算法、训练方式、计算细节）、实验分析、第一性原理重构和文献定位。

## 核心原则

- 所有输出文件必须使用中文，公式、变量名、模型名、数据集名等可保留原文。
- 每个事实性判断都必须能追溯到论文证据。
- 翻译文件只做忠实转述，不加入独立批判；重点复原每个章节和段落组的讲述逻辑。
- 分析文件必须区分论文证据和推断判断。
- 证据不足时明确写出：`论文未提供足够证据。`
- 表格、图、公式、算法中的核心信息不能跳过；附录和补充实验按其精神、证据价值和关键结论概括，除非其中包含理解方法必需的内容。

## 安装

### Codex

将本仓库作为 skill 目录安装到 Codex skill 库：

```bash
git clone https://github.com/V1staz/DeepPaperReader4Chinese.git ~/.codex/skills/paper-reader
```

重启 Codex 后即可使用。

### 旧版 Claude Code

如果你的环境仍使用单文件 Claude Code skill：

```bash
cp paper-reader.md ~/.claude/skills/
```

## 使用

```text
Use $paper-reader to analyze /path/to/paper.pdf
```

也可以直接说“读一下这篇论文”“深度分析这个 PDF”，并提供论文路径。

快速报告模式：

```text
Use $paper-reader to make a fast report for /path/to/paper.pdf
```

也可以说“快速读这篇论文”“生成速读报告”，并提供论文路径。

## 许可

MIT
