# Paper Reader

**English** | [中文](README.md)

A Codex skill for deep academic paper reading. Given a PDF paper, it creates a full Chinese translation and a Chinese research-level analysis focused on reconstructing the authors' reasoning, dissecting the method, interpreting experimental signals, exposing weaknesses, and deriving future research opportunities.

This repository also keeps compatibility with the older single-file Claude Code skill format:

- `SKILL.md`: standard Codex skill entrypoint.
- `paper-reader.md`: legacy single-file Claude Code skill.
- `agents/openai.yaml`: Codex UI metadata.

## Outputs

1. `<paper>_translation.md`: full Chinese translation preserving structure, logical flow, technical details, experimental findings, and formulas.
2. `<paper>_analysis.md`: Chinese research-level analysis covering task formulation, challenges, insights and novelty, method dissection, experiments, weaknesses, future directions, first-principles reconstruction, literature positioning, and researcher takeaways.

## Principles

- All output files must be Chinese, except formulas, variable names, model names, dataset names, benchmarks, and code-like identifiers.
- Every factual claim must be traceable to paper evidence.
- The translation file should be faithful and should not add independent critique.
- The analysis file must separate paper evidence from interpretation.
- If evidence is insufficient, explicitly write: `论文未提供足够证据。`
- Important tables, figures, equations, algorithms, and appendices must not be skipped.

## Installation

### Codex

Install this repository as a Codex skill directory:

```bash
git clone https://github.com/V1staz/DeepPaperReader4Chinese.git ~/.codex/skills/paper-reader
```

Restart Codex after installation.

### Legacy Claude Code

If your environment still uses the single-file Claude Code skill format:

```bash
cp paper-reader.md ~/.claude/skills/
```

## Usage

```text
Use $paper-reader to analyze /path/to/paper.pdf
```

You can also ask in natural language, such as "read this paper" or "deeply analyze this PDF", and provide the paper path.

## License

MIT
