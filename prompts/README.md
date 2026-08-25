# AI Prompt Snippets

一组可复用的 AI 提示词。一级索引只用一条分类轴——**这个 Prompt 的输出流向哪里**：

- **透镜 Lens**：输出是给**你自己**形成理解、视角或判断的（哪怕写成了长报告/说明书）。用完后你的认知变了，但还没产出要交付的东西。文件在 [`lens/`](lens/)。
- **锻造 Forge**：输出**作为工作物流转到下游**——进 PR、发给别人、交付研发、写进文档。文件在 [`forge/`](forge/)。
- **约定 Meta**：不被单次调用，而是**持续生效的背景规则/配置**。文件在 [`meta/`](meta/)。

三类概念正交，先问"输出给谁用"即可无歧义归位。上传新文件的判定顺序见文末[自动分类引导流程](#自动分类引导流程)。

**使用场景**标签是第二维度，标注这个 Prompt 平时在什么情境下用：`工作`（推进具体工作任务）、`思考`（打开思路、换视角）、`决策`（帮你在选项间做判断）、`自我`（认识自己、规划人生）。

---

## 透镜 Lens

改变你看问题的方式，产出理解、视角或判断，供你自己消费。

| Prompt | 关键词 | 使用场景 | 说明 |
|--------|--------|----------|------|
| [苏格拉底式提问](lens/socrates.md) | `!p_socrates` | 思考 | 通过追问找到真正值得回答的问题 |
| [第一性原理](lens/first.md) | `!p_first` | 思考 | 回归基本事实重新推导路径 |
| [第一性原理（短）](lens/one.md) | `!p_one` | 思考 | 一句话思维触发器 |
| [双层解释法](lens/dual.md) | `!p_dual` | 思考 | 小白版 + 专业版双视角学习 |
| [反向拆解](lens/reverse.md) | `!p_reverse` | 思考 | 拆解优秀范例的成功机制 |
| [跨领域借解](lens/cross.md) | `!p_cross` | 思考 | 从其他领域借用底层相通的解法 |
| [事实核查](lens/fact.md) | `!p_fact` | 决策 | 拆分事实/结论/判断并逐项验证 |
| [双向钢人论证](lens/steelman.md) | `!p_steelman` | 决策 | 为两个方向各构建最强理由再判断 |
| [最小实验替代空想](lens/exp.md) | `!p_exp` | 决策 | 设计 7 天可完成的低成本验证实验 |
| [专家会诊](lens/panel.md) | `!p_panel` | 决策 | 多视角互补 + 互相质疑出方案 |
| [圆桌讨论](lens/roundtable.md) | - | 思考 | 多方代表人物求真式结构化深度对话 |
| [横纵分析法](lens/hv.md) | `!p_hv` | 工作 | 纵向历史 × 横向竞品的深度研究 |
| [商业结构](lens/company-structure.md) | - | 思考 | 三才结构拆解公司全生命周期的涡漩演变 |
| [挖掘隐藏天赋](lens/talent.md) | `!p_talent` | 自我 | 多轮对话找到被忽视的底层能力 |
| [人生设计术](lens/life.md) | `!p_life` | 自我 | 斯坦福人生设计法 × 三个奥德赛计划 |

---

## 锻造 Forge

接受输入、交付一份具名格式的产物，产出流转到下游或交付他人。

| Prompt | 关键词 | 使用场景 | 说明 |
|--------|--------|----------|------|
| [代码审查](forge/cr.md) | `!p_cr` | 工作 | 对抗性 Code Review |
| [Bug 排查](forge/bug.md) | `!p_bug` | 工作 | 线上问题根因分析 |
| [架构分析](forge/arch.md) | `!p_arch` | 工作 | 系统/模块架构评审 |
| [PRD 撰写](forge/prd.md) | `!p_prd` | 工作 | 产品需求文档 |
| [撰写技术文档](forge/tech.md) | `!p_tech` | 工作 | 结构化技术方案 |
| [绘流程图](forge/mermaid.md) | `!p_mermaid` | 工作 | Mermaid 图约束生成 |
| [结论先行](forge/rebuild.md) | `!p_rebuild` | 工作 | 去冗余、直达结论 |
| [精简表达](forge/refine.md) | `!p_refine` | 工作 | 工作消息多版本精简 |
| [总结](forge/sum.md) | `!p_sum` | 工作 | 结论先行的内容摘要 |
| [中英互译](forge/trans.md) | `!p_trans` | 工作 | 技术术语精准翻译 |

---

## 约定 Meta

不被单次调用，而是持续生效的协作规则与配置。

| 文件 | 关键词 | 使用场景 | 说明 |
|--------|--------|----------|------|
| [CLAUDE.md](meta/CLAUDE.md) | - | 工作 | 项目编码约定 + SDD 文档准则 |
| [raycast-prompt-snippets.json](meta/raycast-prompt-snippets.json) | - | 工作 | 所有 Prompt 的 Raycast Snippets 导入文件 |

---

## 自动分类引导流程

上传新 Prompt 时，按以下顺序判断归入哪一类（第一个命中即停）：

1. **它是持续生效的背景规则/配置，而非被单次调用的吗？**（如编码约定、全局指令、导入配置）
   → 是 → **约定 Meta**
2. **它的主要输出会作为工作物流转到下游——进 PR、发给别人、交付研发、写进文档吗？**
   → 是 → **锻造 Forge**
3. **它的主要输出是给你自己形成理解、视角或判断（哪怕写成了长报告/说明书）吗？**
   → 是 → **透镜 Lens**

关键区分（避免误判）：**不看是否产出了文档，只看输出给谁用。** 横纵分析、天赋挖掘都产出长文档，但都是给你自己认识对象/自己用的，归 Lens；精简表达虽只出几行字，却要发给别人，归 Forge。

---

## Raycast 快捷片段

[meta/raycast-prompt-snippets.json](meta/raycast-prompt-snippets.json) 是上述所有 Prompt 的 Raycast Snippets 导入文件。

**作用**：将每个 Prompt 注册为 Raycast 的文本片段（Snippet），在任意应用中通过关键词即可展开完整提示词，免去反复复制粘贴。

**使用方式**：
1. 安装 [Raycast](https://www.raycast.com/)（macOS）
2. 打开 Raycast → Import Snippets → 选择此 JSON 文件
3. 在任意输入框中键入关键词（如 `!p_cr`）即可自动展开对应 Prompt

---

## 来源

- 工作效率 & 思维框架：[数字生命卡兹克 — 都Agent时代了，我还是想分享给你这12个我最常用的Prompt](https://mp.weixin.qq.com/s/NAdhdFrUq9-BKelqzqpwBQ)
- 圆桌讨论：[李继刚 — 圆桌讨论Prompt](https://gist.github.com/lijigang/a8f9cf12985d474cef15cda63f4e1892)
- 商业结构：[李继刚 — 商业结构Prompt](https://gist.github.com/lijigang/dd4d2570a196338cbd321757f1cb50d9)
