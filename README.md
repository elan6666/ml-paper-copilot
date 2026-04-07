# ml-paper-copilot

## English

A reusable Codex skill for turning figures, experiment results, Markdown fragments, and scattered notes into a staged manuscript workflow for machine learning, computational biology, and bioinformatics papers.

### Repository Structure

```text
ml-paper-copilot/
├── README.md
├── LICENSE
├── .gitignore
└── ml-paper-copilot/
    ├── SKILL.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        ├── workflow_cn.md
        └── workflow_en.md
```

### What This Skill Does

This skill runs as a five-phase, approval-gated workflow:

1. initialization and configuration confirmation
2. storyline design and outline building
3. modular drafting
4. full-text unification and style alignment
5. typesetting and final QA

The agent must stop after each phase and wait for explicit user approval before continuing.

### Typical Uses

- convert figures and results into a venue-adapted paper plan
- build a paper step by step instead of requesting a one-shot rewrite
- enforce venue-specific structure for Nature-family venues, Bioinformatics, ICLR, NeurIPS, or IEEE
- generate LaTeX and captions only after the narrative is approved
- perform a final manuscript QA pass before submission

### How To Use

Place the `ml-paper-copilot` folder under your Codex skills directory, for example:

- Windows: `%USERPROFILE%\\.codex\\skills\\`
- Cross-platform: `${CODEX_HOME}/skills/`

Then invoke the skill by name when you want a paper-writing workflow rather than a paper-standard checklist.

## 中文

这是一个可复用的 Codex skill，用于把实验结果图、表格、Markdown 草稿、代码说明和零散笔记，转换成一个可审批的论文工作流，适用于机器学习、计算生物学和生物信息学论文。

### 适用场景

- 先设计故事线和大纲，再逐步起草论文
- 依据目标期刊或会议切换章节顺序与摘要格式
- 将图表映射到核心科学主张，而不是直接堆指标
- 在全文批准后再进入 LaTeX 排版与图注整合
- 在最终导出前执行一次严格的排版与引用 QA

### 使用方式

将 `ml-paper-copilot` 文件夹放到你的 Codex skills 目录，例如：

- Windows: `%USERPROFILE%\\.codex\\skills\\`
- 跨平台: `${CODEX_HOME}/skills/`

之后在论文写作任务中按名称调用该 skill。它会以 5 个阶段的状态机方式运行，并在每个阶段结束后停下等待你的批准。

## License

This repository is released under the MIT License.
