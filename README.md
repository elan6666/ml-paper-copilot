# ml-bio-paper-standardizer

## English

A reusable Codex skill for standardizing machine learning and computational biology manuscripts, with a focus on single-cell perturbation prediction papers, benchmark-heavy method papers, and biology-facing ML manuscripts.

### Repository Structure

```text
ml-bio-paper-standardizer/
├── README.md
├── LICENSE
├── .gitignore
└── ml-bio-paper-standardizer/
    ├── SKILL.md
    └── references/
        ├── paper_standards_cn.md
        └── paper_standards_en.md
```

### What This Skill Is For

This skill is suitable for papers such as:

- single-cell perturbation prediction
- computational biology and bioinformatics method papers
- benchmark-heavy ML-for-biology manuscripts
- reference-conditioned, generative, or representation-learning papers

It is especially useful when you need to:

- rewrite abstract, introduction, methods, results, or discussion
- convert metric-heavy results into a claim-driven story chain
- align figures, notebooks, and manuscript structure
- decide which equations should be numbered
- strengthen figure captions without inventing unsupported statistics

### How To Use

Place the `ml-bio-paper-standardizer` folder under your Codex skills directory, for example:

- Windows: `%USERPROFILE%\\.codex\\skills\\`
- Cross-platform: `${CODEX_HOME}/skills/`

Then invoke the skill by name in a task involving paper drafting or revision.

## 中文

这是一个可复用的 Codex skill，用于统一机器学习与计算生物学论文的写作标准，尤其适合单细胞扰动预测、benchmark-heavy 方法论文以及强调生物学解释的 ML 论文。

### 适用场景

它尤其适合以下任务：

- 重写摘要、引言、方法、结果或讨论
- 将“指标堆砌式结果”改写为“主张驱动的故事链”
- 对齐 notebook、图表与论文叙事
- 决定哪些核心公式应该编号
- 扩写图注，但不虚构误差线、样本量或统计检验

### 使用方式

将 `ml-bio-paper-standardizer` 文件夹放到你的 Codex skills 目录，例如：

- Windows：`%USERPROFILE%\\.codex\\skills\\`
- 跨平台：`${CODEX_HOME}/skills/`

之后在论文改写任务中按名称调用即可。

## License

This repository is released under the MIT License.
