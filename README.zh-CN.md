# 意识体迁移 (Consciousness Transfer)

> 将知识转化为能力的四阶段内化方法论。
>
> [English Documentation](./README.md)

**帝王认知体 (Emperor Cognition) 项目的一部分。**

---

## 功能说明

大多数 skill 只展示信息。这个 skill 帮你**内化**它。

```
阶段 1: 感（感悟）  →  情感代入故事
阶段 2: 悟（发现）  →  自己提炼模型（苏格拉底式引导）
阶段 3: 用（应用）  →  用在你的真实场景中
阶段 4: 破（突破）  →  知道它何时失效
```

灵感来源：中国传统教育的四个层次——记、悟、用、化。

---

## 差异化对比

| | 信息卡片类 Skill | 苏格拉底问答类 Skill | **意识体迁移** |
|---|:-:|:-:|:-:|
| 展示思维模型 | ✅ | ✅ | ✅ |
| 引导你自己发现模型 | ❌ | ✅ | ✅ |
| 将模型应用到你的真实场景 | ❌ | ❌ | ✅ |
| 测试模型的失效边界 | ❌ | ❌ | ✅ |
| 生成可保存的使用手册 | ❌ | ❌ | ✅ |

---

## 安装

选择适合你工作流的方式：

### 方式 1：npx（推荐）
```bash
npx skills add ai-x-skills/consciousness-transfer -g -y
```

### 方式 2：Claude Code marketplace（GitHub 远程）
```bash
claude plugin marketplace add https://github.com/ai-x-skills/consciousness-transfer.git --scope user
claude plugin install consciousness-transfer@consciousness-transfer --scope user
```

### 方式 3：本地目录 marketplace
```bash
git clone https://github.com/ai-x-skills/consciousness-transfer.git
claude plugin marketplace add /path/to/consciousness-transfer --scope user
claude plugin install consciousness-transfer@consciousness-transfer --scope user
```

### 方式 4：手动复制
将 `consciousness-transfer/` 目录复制到 `~/.claude/skills/` 或 `~/.claude/local-skills/`。

---

## 快速开始

**第 1 步**：安装（见上方）

**第 2 步**：提供知识条目

三种方式：

**方式 A**（最简单）：用自然语言描述你的场景
```
我是产品经理，在纠结要不要转型。工程团队说继续，销售团队说转型。帮我理清思路。
```
Skill 会自动匹配相关的知识条目，引导你完成整个流程。

**方式 B**：指定 YAML 文件
```
学习这个模型：references/tang_taizong_decision.yaml
```

**方式 C**：内联 YAML
```yaml
title: "兼听则明"
description: "重大决策前主动寻求反对意见"
mental_model:
  - "明确决策事项"
  - "寻找最强反对意见"
  - "寻找最强支持意见"
  - "找到矛盾焦点"
  - "决策 + 追踪"
counter_example: "隋炀帝只听支持者意见，三次征高丽失败"
```

**第 3 步**：跟随 Skill 完成四个阶段

Skill 会自动引导你完成 感 → 悟 → 用 → 破，并生成一份可保存的**使用手册**。

---

## 完整示例

> 用户："我是产品经理，在纠结要不要转型。工程团队说继续，销售团队说转型。我卡住了。"

### 阶段 0：匹配
Skill 将此场景匹配到"兼听则明"条目。

### 阶段 1：感
Skill 讲述唐太宗与魏征的故事——太宗如何通过结构化地寻求最强反对意见来做决策，而非只听最舒服的声音。

> "你觉得他为什么主动去找那个最反对他的人？"

### 阶段 2：悟
Skill 提出递进式问题：
- "当时太宗关注的核心信息是什么？"
- "你有没有发现，他每次做决策前都先做同一件事？"
- "如果把他的方法写成清单，会是什么样？"
- "这个方法什么时候会失效？"

用户逐步自己提炼出模型。

### 阶段 3：用
Skill 回到产品经理的场景：
- "对你来说，第 1 步（明确决策事项）具体是什么？"
- "谁是你最强的反对声音？他最好的论据是什么？"
- "工程和销售的根本分歧在哪？那就是突破口。"

然后交付一份行动清单。

### 阶段 4：破
Skill 讲述反例：隋炀帝不顾满朝反对，三次征高丽皆败。

> "如果你的团队已经有了强烈先入之见，'兼听则明'会怎样变成走过场？"

用户获得一份**使用手册**，包含适用边界、失效信号和替代模型。

---

## 知识条目格式

```yaml
title: "简短标签"
description: "2-4 句话解释"
mental_model:
  - "步骤 1"
  - "步骤 2"
  - "步骤 3"
context_trigger: "什么场景下使用"
decision_tree:
  "条件": "行动"
modern_parallel: "现代场景类比"
counter_example: "何时/何地此模型失效"
effectiveness: "effective | mixed | destructive"
confidence: 0.85
source_text: "原始史料"
source_citation: "出处引用"
```

参见 [`references/`](./references/) 目录中的完整示例：
- [`tang_taizong_decision.yaml`](./references/tang_taizong_decision.yaml) — 唐太宗兼听则明决策框架
- [`munger_multimodel.yaml`](./references/munger_multimodel.yaml) — 芒格多元思维模型

---

## 方法论

### 为什么是四个阶段？

四阶段对应中国传统教育的四个层次：

| 阶段 | 古文 | 发生什么 | 为什么有效 |
|------|------|---------|-----------|
| 感 | 感 | 通过故事产生情感代入 | 叙事记忆比事实记忆更持久 |
| 悟 | 悟 | 用户自己提炼出模型 | 通过主动输出构建回忆路径 |
| 用 | 用 | 迁移到用户真实场景 | 通过实践构建应用路径 |
| 破 | 化 | 探索失效边界 | 防止过度应用，构建元认知 |

### 核心洞见

> 能回忆但不能用的知识不是技能。
> 能用但不知道边界的技能是危险的。
> 意识体迁移同时构建能力和智慧。

---

## 项目结构

```
consciousness-transfer/
  .claude-plugin/
    plugin.json              # 插件身份清单
    marketplace.json         # Marketplace 清单（用于发现和安装）
  references/
    tang_taizong_decision.yaml   # 唐太宗兼听则明决策框架
    munger_multimodel.yaml       # 芒格多元思维模型
  SKILL.md                   # Skill 核心指令
  README.md                  # 英文文档
  README.zh-CN.md            # 本文件
  LICENSE                    # MIT 许可证
```

---

## 帝王认知体项目

本 skill 是更大系统的一环：

```
采集 → 萃取 → 验证 → 迁移
  ↓       ↓       ↓       ↓
原始    意识体    质量     内化
素材    萃取      门控   （本 skill）
```

- 帝王认知体 (Emperor Cognition) 项目
- 17 种来自中国帝王将相的认知模块
- 5 项质量测试框架
- 双层描述法（历史层 + 抽象层）

---

## 许可证

MIT
