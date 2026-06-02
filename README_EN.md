# Paper Reader — Claude Code Skill

**English** | [中文](README.md)

Deep academic paper analysis skill for Claude Code. Goes far beyond summarization: reconstructs the authors' reasoning from first principles, identifies core insights, exposes limitations, and derives future research directions.

## What It Does

Given a PDF paper, this skill produces two comprehensive markdown files:

1. **`<paper>_translation.md`** — Full Chinese translation preserving document hierarchy, logical flow, and technical detail.

2. **`<paper>_analysis.md`** — Research-level analysis covering:
   - **Task** — Formal problem definition, inputs/outputs, optimization objective
   - **Challenge** — Why existing methods fail, with evidence
   - **Insight & Novelty** — Reconstructed reasoning, core insights, innovations with problem/insight/design/implementation/mechanism/effect breakdown
   - **Method Dissection** — Component-by-component analysis, information flow, training pipeline
   - **Experimental Analysis** — Beyond what authors claim: hidden findings, scaling behavior
   - **Weaknesses** — Independent critical analysis (scenario, data, architecture, evaluation)
   - **Future Opportunities** — Concrete research directions rated by venue potential
   - **First-Principles Reconstruction** — How a strong researcher could derive this idea from scratch
   - **Literature Relation** — Positioned against classical, baseline, and SOTA methods
   - **Researcher Takeaways** — 30-second, 5-minute, and mindset-level summaries

## Installation

```bash
# Via Claude Code skill marketplace (recommended)
claude skills install paper-reader

# Or manually: copy paper-reader.md to your skills directory
cp paper-reader.md ~/.claude/skills/
```

## Usage

```
/paper-reader /path/to/paper.pdf
```

Or just say "read this paper" or "analyze this paper" and provide the PDF path.

## Requirements

- Claude Code with PDF reading capability
- The PDF must be accessible from the working directory

## Author

Created from the deep-reading analysis framework.

## License

MIT
