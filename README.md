# Paper Reader

[English](README_EN.md) | **中文**

面向 Codex 的学术论文深读技能。给定一篇 PDF 论文后，生成完整中文翻译和研究级中文分析，重点是重构作者推理、拆解方法机制、分析实验信号、暴露潜在弱点，并推导后续研究方向。

本仓库同时保留旧版 Claude Code 单文件用法：

- `SKILL.md`：Codex 标准技能入口。
- `paper-reader.md`：兼容旧版 Claude Code 的单文件技能。
- `agents/openai.yaml`：Codex UI 元数据。

## 生成文件

1. `<论文名>_translation.md`：完整中文翻译，保留原文结构、逻辑流、技术细节、实验发现和公式。
2. `<论文名>_analysis.md`：研究级中文分析，覆盖任务定义、核心挑战、洞察与创新、方法拆解、实验分析、潜在弱点、未来方向、第一性原理重构、文献定位和研究者要点。

## 核心原则

- 所有输出文件必须使用中文，公式、变量名、模型名、数据集名等可保留原文。
- 每个事实性判断都必须能追溯到论文证据。
- 翻译文件只做忠实转述，不加入独立批判。
- 分析文件必须区分论文证据和推断判断。
- 证据不足时明确写出：`论文未提供足够证据。`
- 表格、图、公式、算法和附录中的关键信息不能跳过。

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

## 许可

MIT
