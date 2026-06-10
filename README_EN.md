# Paper Reader

**English** | [中文](README.md)

A Codex skill for academic paper reading. Given a PDF paper, it can create the full pair of a concise Chinese translated reading note and a Chinese research-level analysis, or a single Chinese fast report. It focuses on reconstructing the authors' reasoning, dissecting the method, interpreting experimental signals, exposing weaknesses, and deriving future research opportunities.

This repository also keeps compatibility with the older single-file Claude Code skill format:

- `SKILL.md`: standard Codex skill entrypoint.
- `paper-reader.md`: legacy single-file Claude Code skill.
- `agents/openai.yaml`: Codex UI metadata.

## Outputs

Full mode creates:

1. `<paper>_translation.md`: concise Chinese translated reading note preserving section structure, author logic, core algorithms, key technical details, major experimental findings, and formulas without translating word by word.
2. `<paper>_analysis.md`: Chinese research-level analysis covering task formulation, challenges, insights and novelty, method dissection, experiments, weaknesses, future directions, first-principles reconstruction, literature positioning, and researcher takeaways.

Fast-report mode creates:

1. `<paper>_fastreport.md`: a single Chinese fast report covering task definition, concrete method details including algorithms, training and computation details, experiment analysis, first-principles reconstruction, and literature positioning.

## Principles

- All output files must be Chinese, except formulas, variable names, model names, dataset names, benchmarks, and code-like identifiers.
- Every factual claim must be traceable to paper evidence.
- The translation file should be faithful, should not add independent critique, and should focus on reconstructing each section's and paragraph group's logic.
- The analysis file must separate paper evidence from interpretation.
- If evidence is insufficient, explicitly write: `论文未提供足够证据。`
- Core information from tables, figures, equations, and algorithms must not be skipped. Appendices and supplementary experiments should be summarized by their spirit, evidence value, and key conclusions unless they are necessary for understanding the method.

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

Fast-report mode:

```text
Use $paper-reader to make a fast report for /path/to/paper.pdf
```

You can also ask for a quick read or fast report in natural language and provide the paper path.

## License

MIT
