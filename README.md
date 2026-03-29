# Humanizer — Academic Writing Normalization Engine

> Transform AI-generated or rigid text into academically natural, structurally varied, and discipline-consistent writing.

[![Version](https://img.shields.io/badge/version-3.0.0-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

---

## What it does

Humanizer is a **Claude skill** that normalizes AI-generated academic text through a multi-stage processing pipeline. It does not "humanize" text in a casual or expressive way — instead, it eliminates the statistical monotony in structure, syntax, and rhythm that makes AI writing detectable.

### The pipeline

```
Input Text
    │
    ▼
┌─────────────────────────────────────┐
│  STAGE 1: Structural Recomposition  │
│  Reorganize sentences & clauses     │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  STAGE 2: Linguistic Normalization  │
│  Refine vocabulary & voice          │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  STAGE 3: Pattern Disruption        │
│  Vary rhythm, length & transitions  │
└──────────────┬──────────────────────┘
               │
               ▼
┌─────────────────────────────────────┐
│  FINAL VALIDATION                   │
│  Verify meaning, citations & tone   │
└──────────────┬──────────────────────┘
               │
               ▼
         Final Output
```

---

## Installation

### Option A: Download as ZIP (recommended for Claude skill upload)

1. Download the repository as a ZIP file from GitHub.
2. Extract the ZIP.
3. Upload the `SKILL.md` file directly to Claude as a skill/project file.

### Option B: Clone into Claude Code skills directory

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/csdee/Humanizer_tii.git ~/.claude/skills/humanizer
```

### Option C: Manual copy

```bash
mkdir -p ~/.claude/skills/humanizer
cp SKILL.md ~/.claude/skills/humanizer/
```

---

## Usage

### In Claude (via uploaded skill)

Simply paste your academic text and the skill will automatically process it through all four stages, returning only the normalized output.

### In Claude Code

```
/humanizer

[paste your academic text here]
```

---

## Processing stages

### Stage 1 — Structural Recomposition
Reorganizes sentence structure by merging, splitting, and reordering clauses. Varies information flow so text does not follow a rigid subject-verb-object pattern throughout.

### Stage 2 — Linguistic Normalization
Reduces unnecessary passive voice, replaces inflated vocabulary with precise alternatives, eliminates fake hedging, and reduces nominalizations where clarity improves.

### Stage 3 — Pattern Disruption and Variation
Varies sentence length, avoids repetitive transitions, introduces syntactic diversity, and ensures non-uniform rhythm across paragraphs.

### Final Validation
Verifies that meaning is unchanged, all citations are preserved, no informal tone was introduced, and sentence structures are sufficiently varied. Fixes any issues internally before output.

---

## User controls

The skill supports three adjustable parameters:

| Parameter | Options | Default | Description |
|---|---|---|---|
| **Formality Level** | High | High | Maintains strict academic register |
| **Structural Variation** | Medium / High | Medium | Degree of sentence reorganization |
| **Lexical Simplicity** | Low / Medium / High | Low | How aggressively to simplify vocabulary |

---

## 25 AI writing patterns detected

The skill includes a comprehensive reference of 25 known AI writing patterns, sourced from [Wikipedia's "Signs of AI writing"](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) guide.

### Content patterns (1–6)
| # | Pattern | Example fix |
|---|---------|-------------|
| 1 | Significance inflation | "marking a pivotal moment" → removed |
| 2 | Notability name-dropping | Source list → specific cited claim |
| 3 | Superficial -ing analyses | Dangling participles → removed or expanded |
| 4 | Promotional language | "nestled within breathtaking" → "is a town in" |
| 5 | Vague attributions | "Experts believe" → specific source cited |
| 6 | Formulaic challenges | "Despite challenges... thrives" → specific facts |

### Language patterns (7–12)
| # | Pattern | Example fix |
|---|---------|-------------|
| 7 | AI vocabulary words | "Additionally... testament... landscape" → plain terms |
| 8 | Copula avoidance | "serves as" → "is" |
| 9 | Negative parallelisms | "Not just X, it's Y" → state point directly |
| 10 | Rule of three | Forced triplets → natural grouping |
| 11 | Synonym cycling | Rotating synonyms → consistent terminology |
| 12 | False ranges | "from X to Y" → list items directly |

### Style patterns (13–18, 25)
| # | Pattern | Example fix |
|---|---------|-------------|
| 13 | Em dash overuse | Em dashes → commas or periods |
| 14 | Boldface overuse | Mechanical bold → plain text |
| 15 | Inline-header lists | Bold-colon lists → prose |
| 16 | Title Case headings | "All Words Capitalized" → sentence case |
| 17 | Emojis | Decorative emojis → removed |
| 18 | Curly quotes | Curly → straight quotes |
| 25 | Hyphenated pairs | "cross-functional" → "cross functional" |

### Communication patterns (19–21)
| # | Pattern | Example fix |
|---|---------|-------------|
| 19 | Chatbot artifacts | "I hope this helps!" → removed |
| 20 | Cutoff disclaimers | "While details are limited..." → find source or remove |
| 21 | Sycophantic tone | "Great question!" → removed |

### Filler and hedging (22–24)
| # | Pattern | Example fix |
|---|---------|-------------|
| 22 | Filler phrases | "In order to" → "To" |
| 23 | Excessive hedging | "could potentially possibly" → "may" |
| 24 | Generic conclusions | "The future looks bright" → specific plans |

---

## Key principles

- **Preserve meaning exactly** — no factual changes, no hallucinations.
- **Preserve all citations** — references and technical terms stay intact.
- **Academic tone only** — no opinions, storytelling, or personal voice.
- **Eliminate statistical monotony** — not optimizing for "AI detection scores", but removing the patterns that make text detectable.
- **Clarity over complexity** — do not add unnecessary complexity.

---

## Version history

| Version | Changes |
|---|---|
| **3.0.0** | Complete rewrite: multi-stage pipeline (Structural Recomposition → Linguistic Normalization → Pattern Disruption → Final Validation), added USER CONTROLS, academic-focused identity, removed casual humanization |
| **2.3.0** | Added pattern #25: hyphenated word pair overuse |
| **2.2.0** | Added final "obviously AI generated" audit + second-pass rewrite |
| **2.1.1** | Fixed pattern #18 example (curly vs straight quotes) |
| **2.1.0** | Added before/after examples for all 24 patterns |
| **2.0.0** | Complete rewrite based on raw Wikipedia article content |
| **1.0.0** | Initial release |

---

## References

- [Wikipedia: Signs of AI writing](https://en.wikipedia.org/wiki/Wikipedia:Signs_of_AI_writing) — primary source for pattern definitions
- [WikiProject AI Cleanup](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_AI_Cleanup) — maintaining organization

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
