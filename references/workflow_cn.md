# ML Paper Copilot - 两阶段工作流

## 0. 总体规则

这是一个严格的两阶段流程。

- Phase 0 是唯一停顿点。
- Phase 1 必须一次性执行到底，不再追加用户确认。
- 全部规则只能来自本仓库自带的 references 和 templates。

## Phase 0: 初始化与拦截

必须收集并确认以下输入：

1. 目标期刊、会议或目标模板
2. 图表、结果材料或明确说明当前暂无
3. 结果摘要、Markdown 碎片或实验笔记
4. `.bib` 文件
5. 文风偏好

如条件允许，应额外要求：
- 每张图的一句话结论
- 3 到 5 条核心贡献 bullet

如果有必需输入缺失，只能在这里追问。用户确认后立即进入 Phase 1，之后不得再次停顿。

## Phase 1: 端到端执行

### Step A: 故事线设计
- 仅基于用户提供的材料提取核心主张
- 建立符合目标 venue 的章节顺序和图表到主张的映射
- 确保结果章节围绕科学主张，而不是指标堆砌

### Step B: 状态机接力起草
- 以本地 `templates/paper-state.yaml` 作为内部状态结构
- 按章节或小节逐段起草
- 每完成一个部分，都要压缩成简短 state 摘要
- 后续章节只能基于 state 加原始材料继续，而不是依赖无限累积上下文

### Step C: 内部静默自审
- 使用本地 `references/red-team-review.md` 做魔鬼代言人式攻击
- 使用本地 `references/methodology-checks.md` 做方法学核查
- 使用本地 `references/section-checklist.md` 做章节完整性检查
- 如果仍存在 CRITICAL 或 MAJOR 问题，必须内部重写并复查
- 不得向用户展示内部批评过程

### Step D: 本地模板注入与 `.bib` 织入
- 只能从 `templates/` 中选择模板
- 使用 `references/template-selection.md` 中的 venue 映射规则
- 直接把内容注入选定模板，而不是自由手写整套 LaTeX 结构
- 引用只能来自用户提供的 `.bib`
- 只有 key 存在时才允许插入 `\cite{}`
- 缺失引用或 fallback 模板必须记录在 QA 中，不能伪造条目

## 最终输出

一次性返回：

1. 基于本地模板生成的最终 LaTeX 源码
2. 简短 QA 报告，说明残留风险、缺失输入、引用缺口以及模板 fallback 情况
