# Consciousness Transfer

> A four-phase methodology for turning knowledge into skill.
> 将知识转化为能力的四阶段内化方法论。

**Part of the [Emperor Cognition](https://github.com/XaviLau/emperors-cc-aura) project.**

---

## What This Does

Most skills show you information. This one helps you **internalize** it.

```
Phase 1: Feel     →  Enter the story emotionally
Phase 2: Discover →  Articulate the model yourself (Socratic)
Phase 3: Apply    →  Use it in your real situation
Phase 4: Stress   →  Know when it fails
```

感悟用破 — inspired by Chinese classical education: 记 (memorize), 悟 (comprehend), 用 (apply), 化 (internalize).

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

## Quick Start

**Step 1**: Install
```bash
npx skills add <owner>/consciousness-transfer -g -y
```

**Step 2**: Provide a knowledge entry
```yaml
title: "兼听则明"
description: "Seek opposing viewpoints before deciding"
mental_model: ["Identify the decision", "Seek strongest反对", "Seek strongest支持", "Find the contradiction", "Decide + track"]
counter_example: "隋炀帝只听支持者意见，三次征高丽失败"
```

**Step 3**: Let the skill guide you through four phases

---

## How It Works: A Complete Example

> User: "I'm a product manager deciding whether to pivot our product. The engineering team says stay, the sales team says pivot. I'm stuck."

### Phase 0: Match
The skill matches this to the "兼听则明" (Seek Opposing Views) entry.

### Phase 1: Feel
The skill tells the story of Tang Taizong and Wei Zheng — how Taizong structured decision-making by seeking the strongest反对意见, not just the most comfortable one.

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
- "Who is your strongest反对 voice? What's their best argument?"
- "Where do engineering and sales fundamentally differ? That's your breakthrough point."

Then delivers an action checklist.

### Phase 4: Stress-test
The skill tells the counter-example: Emperor Yang of Sui ignored unanimous反对 and launched three failed campaigns.

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

See [`examples/`](./examples/) for complete examples:
- [`tang_taizong_decision.yaml`](./examples/tang_taizong_decision.yaml) — Tang Taizong's decision framework (唐太宗兼听则明)
- [`munger_multimodel.yaml`](./examples/munger_multimodel.yaml) — Charlie Munger's latticework of mental models

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

能回忆但不能用的知识不是技能。能用但不知道边界的技能是危险的。意识体迁移同时构建能力和智慧。

---

## Part of Emperor Cognition

This skill is one piece of a larger system:

```
Scrape → Extract → Validate → Transfer
  ↓         ↓          ↓          ↓
Source    Consciousness  Quality   Internalization
Material  Extraction     Gate      (this skill)
```

- [Emperor Cognition Project](https://github.com/XaviLau/emperors-cc-aura)
- 17 cognitive modules from Chinese imperial history
- 5-test quality framework
- Dual-layer description method (historical + abstract)

---

## License

MIT
