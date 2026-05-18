# Consciousness Transfer

> A four-phase methodology for turning knowledge into skill.
>
> [中文文档 / Chinese Documentation](./README.zh-CN.md)

**Part of the Emperor Cognition (帝王认知体) project.**

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
Learn this model: references/tang_taizong_decision.yaml
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
- [`tang_taizong_decision.yaml`](./references/tang_taizong_decision.yaml) — Tang Taizong's decision framework
- [`munger_multimodel.yaml`](./references/munger_multimodel.yaml) — Charlie Munger's latticework of mental models

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
    tang_taizong_decision.yaml   # Tang Taizong's decision framework
    munger_multimodel.yaml       # Charlie Munger's latticework of mental models
  SKILL.md                   # Core skill instructions
  README.md                  # This file
  README.zh-CN.md            # Chinese documentation
  LICENSE                    # MIT License
```

---

## Part of Emperor Cognition

This skill is one piece of a larger system:

```
Scrape → Extract → Validate → Transfer
  ↓         ↓          ↓          ↓
Source    Consciousness  Quality   Internalization
Material  Extraction     Gate      (this skill)
```

- Emperor Cognition (帝王认知体) project
- 17 cognitive modules from Chinese imperial history
- 5-test quality framework
- Dual-layer description method (historical + abstract)

---

## License

MIT
