# Consciousness Transfer

> A four-phase methodology for turning knowledge into skill.
>
> [中文文档 / Chinese Documentation](./README.zh-CN.md)

**Part of the [Emperor's Aura (帝王认知体)](https://github.com/ai-x-soul/emperors-aura) project.**

---

## What This Does

Most skills show you information. This one helps you **internalize** it.

```
Phase 1: Feel     →  Enter the story emotionally
Phase 2: Discover →  Articulate the model yourself (Socratic)
Phase 3: Apply    →  Use it in your real situation
Phase 4: Stress   →  Know when it fails
```

Inspired by Chinese classical education: 记 (memorize), 悟 (comprehend), 用 (apply), 化 (internalize).

---

## What Makes This Different

| | Reference Cards | Socratic Skills | **Consciousness Transfer** |
|---|:-:|:-:|:-:|
| Shows you the model | ✅ | ✅ | ✅ |
| Guides you to discover it yourself | ❌ | ✅ | ✅ |
| Applies it to your real situation | ❌ | ❌ | ✅ |
| Tests its failure boundaries | ❌ | ❌ | ✅ |
| Produces a Usage Manual you can keep | ❌ | ❌ | ✅ |

---

## Installation

Choose any method that suits your workflow:

### Method 1: npx (recommended)
```bash
npx skills add ai-x-skills/consciousness-transfer -g -y
```

### Method 2: Claude Code marketplace (GitHub)
```bash
claude plugin marketplace add https://github.com/ai-x-skills/consciousness-transfer.git --scope user
claude plugin install consciousness-transfer@consciousness-transfer --scope user
```

### Method 3: Local directory marketplace
```bash
git clone https://github.com/ai-x-skills/consciousness-transfer.git
claude plugin marketplace add /path/to/consciousness-transfer --scope user
claude plugin install consciousness-transfer@consciousness-transfer --scope user
```

### Method 4: Manual copy
Copy the `consciousness-transfer/` directory to `~/.claude/skills/` or `~/.claude/local-skills/`.

---

## Quick Start

**Step 1**: Install (see above)

**Step 2**: Provide a knowledge entry

You can provide a knowledge entry in three ways:

**Option A** (easiest): Describe your situation in natural language
```
I'm a product manager deciding whether to pivot. The engineering team
says stay, the sales team says pivot. Help me think through this.
```
The skill will match your situation to a relevant knowledge entry and guide you through it.

**Option B**: Point to a YAML file
```
Learn this model: references/tang_taizong_opposing_views.yaml
```

**Option C**: Inline YAML in your message
```yaml
title: "兼听则明"
description: "Seek opposing viewpoints before deciding"
mental_model:
  - "Identify the decision"
  - "Seek strongest opposing arguments"
  - "Seek strongest supporting arguments"
  - "Find the contradiction"
  - "Decide + track"
counter_example: "Emperor Yang of Sui ignored unanimous opposition and launched three failed campaigns"
```

**Step 3**: Let the skill guide you through four phases

The skill will automatically walk you through Feel → Discover → Apply → Stress-test, and produce a Usage Manual you can keep.

---

## How It Works: A Complete Example

> User: "I'm a product manager deciding whether to pivot our product. The engineering team says stay, the sales team says pivot. I'm stuck."

### Phase 0: Match
The skill matches this to the "Seek Opposing Views" (兼听则明) entry.

### Phase 1: Feel
The skill tells the story of Tang Taizong and Wei Zheng — how Taizong structured decision-making by seeking the strongest opposing viewpoint, not just the most comfortable one.

> "Why do you think he actively sought the person who disagreed most?"

### Phase 2: Discover
The skill asks progressive questions:
- "At that point, what information did Taizong focus on?"
- "Did you notice he always did the same thing before deciding?"
- "If you wrote his method as a checklist, what would it look like?"
- "When would this method NOT work?"

The user gradually articulates the model themselves.

### Phase 3: Apply
The skill returns to the PM's situation:
- "What does Step 1 (identify the decision) look like for you?"
- "Who is your strongest opposing voice? What's their best argument?"
- "Where do engineering and sales fundamentally differ? That's your breakthrough point."

Then delivers an action checklist.

### Phase 4: Stress-test
The skill tells the counter-example: Emperor Yang of Sui ignored unanimous opposition and launched three failed campaigns.

> "If your team already has a strong prior, how would 'seeking opposing views' become performative?"

The user gets a **Usage Manual** with applicable boundaries, failure signals, and alternative models.

---

## Knowledge Entry Format

```yaml
title: "Short label"
description: "2-4 sentence explanation"
mental_model:
  - "Step 1"
  - "Step 2"
  - "Step 3"
context_trigger: "When to use this"
decision_tree:
  "Condition": "Action"
modern_parallel: "Modern scenario"
counter_example: "When/where this failed"
effectiveness: "effective | mixed | destructive"
confidence: 0.85
source_text: "Original source"
source_citation: "Reference"
```

See [`references/`](./references/) for complete examples:
- [`tang_taizong_opposing_views.yaml`](./references/tang_taizong_opposing_views.yaml) — Tang Taizong's opposing views framework (兼听则明)
- [`han_wudi_multi_board.yaml`](./references/han_wudi_multi_board.yaml) — Han Wudi's multi-board parallel game (多棋盘并行博弈)
- [`ming_taizu_borrow_momentum.yaml`](./references/ming_taizu_borrow_momentum.yaml) — Ming Taizu's borrow-momentum model (借势立威独行)
- [`song_zhaopu_institutional_erosion.yaml`](./references/song_zhaopu_institutional_erosion.yaml) — Zhao Pu's institutional erosion method (制度蚕食法)
- [`modern_munger_latticework.yaml`](./references/modern_munger_latticework.yaml) — Charlie Munger's latticework of mental models

---

## The Methodology

### Why Four Phases?

The four phases map to how Chinese classical education worked:

| Phase | Chinese | What Happens | Why It Works |
|-------|---------|-------------|-------------|
| Feel | 感 | Emotional engagement through story | Narrative memory is stronger than factual memory |
| Discover | 悟 | User articulates the model through questions | Building recall pathways through active production |
| Apply | 用 | Transfer to user's real situation | Building application pathways through practice |
| Stress | 破 | Explore failure boundaries | Prevents over-application and builds meta-cognition |

### The Core Insight

> Knowledge that you can recall but cannot apply is not skill.
> Knowledge that you can apply but do not know its limits is dangerous.
> Consciousness Transfer builds both ability AND wisdom.

---

## Project Structure

```
consciousness-transfer/
  .claude-plugin/
    plugin.json              # Plugin identity manifest
    marketplace.json         # Marketplace manifest for discovery & install
  references/
    tang_taizong_opposing_views.yaml       # Tang Taizong's opposing views framework (兼听则明)
    han_wudi_multi_board.yaml              # Han Wudi's multi-board parallel game (多棋盘并行博弈)
    modern_munger_latticework.yaml         # Charlie Munger's latticework of mental models
    ming_taizu_borrow_momentum.yaml        # Ming Taizu's borrow-momentum model (借势立威独行)
    song_zhaopu_institutional_erosion.yaml # Zhao Pu's institutional erosion method (制度蚕食法)
  SKILL.md                   # Core skill instructions
  README.md                  # This file
  README.zh-CN.md            # Chinese documentation
  LICENSE                    # MIT License
```

---

## Part of Emperor's Aura

This skill is the **delivery layer** of the [Emperor's Aura](https://github.com/ai-x-soul/emperors-aura) (帝王认知体) project — a system that extracts transferable cognitive patterns from Chinese imperial history.

### Data Pipeline

```
Scrape → Extract → Validate → Transfer
  ↓         ↓          ↓          ↓
Source    Consciousness  Quality   Internalization
Material  Extraction     Gate      (this skill)
```

- **Upstream**: [Emperor's Aura](https://github.com/ai-x-soul/emperors-aura) — scrapes historical sources, extracts consciousness entities via Claude API, validates with a 5-test quality framework
- **This skill**: Takes validated knowledge entries and guides users through the four-phase internalization process

### The 17 Cognitive Modules

Emperor's Aura defines 17 transferable thinking modules across three categories:

**Emperor's 8 Operating Systems**: decision framework, people reading, game theory, crisis psychology, power cognition, era insight, failure patterns, growth arc

**Minister's 4 Operating Systems**: advisory framework, influence mechanism, survival intelligence, reform methodology

**Emperor-Minister Interactions**: cognitive complement, cognitive clash, cognitive transplant, *shi* cognition, timing wisdom

### Current Coverage

The 5 bundled entries in `references/` are curated samples. Emperor's Aura has extracted **112+ consciousness entities** covering Han, Tang, Song, Ming, Qing dynasties and more. As the upstream project matures, additional entries can be added to this skill.

### Quality Framework

Every knowledge entry passes Emperor's Aura's 5-test validation (transferability, specificity, falsifiability, evidence, counter-example), scored 0–5.0. Entries below 3.0 are re-extracted. The bundled entries in this skill are curated from passing entities.

### Extending with New Entries

You can create your own knowledge entries following the [YAML format](#knowledge-entry-format) and drop them into `references/`. For high-quality, historically validated entries, see the [Emperor's Aura data pipeline](https://github.com/ai-x-soul/emperors-aura).

---

## License

MIT
