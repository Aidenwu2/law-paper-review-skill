# Law Paper Review Skill - 法学论文多专家并行自查

一个 [Claude Code](https://claude.com/claude-code) 自定义 Skill，模拟 **8 位不同角色的专家同时审查论文**，覆盖方法论、文献、写作、合规、期刊匹配、答辩模拟、实证复现和图表审美，最终汇总为一份综合审查报告。

## 特性

- **8 位 AI 专家并行审查**，一次性启动，互不干扰
- 支持 **中文（CLSCI）** 和 **英文（SSCI）** 法学论文
- 尤其适合 **实证法学 / 法律经济学** 方向
- 自动输出结构化的综合审查报告

### 8 位专家

| # | 专家角色 | 审查维度 |
|---|---------|---------|
| 1 | 方法论审稿人 | 因果推断、内生性、统计方法、稳健性检验 |
| 2 | 文献审稿人 | 文献覆盖、引用准确性、创新性、理论框架 |
| 3 | 写作与结构审稿人 | 标题、摘要、结构、语言、逻辑连贯性 |
| 4 | 学术合规审查员 | 学术诚信、伦理合规、参考文献格式 |
| 5 | 期刊匹配顾问 | 期刊推荐、匹配度分析、投稿策略 |
| 6 | 答辩模拟官 | 犀利提问、硬伤诊断、回应策略 |
| 7 | 实证复现审查员 | 数据可获取性、变量透明度、代码规范 |
| 8 | 图表审美审查员 | 三线表、配色、分辨率、图表类型选择 |

## 安装

1. 确保已安装 [Claude Code](https://claude.com/claude-code)
2. 创建 skill 目录：

```bash
mkdir -p ~/.claude/skills/law-paper-review
```

3. 复制 skill 文件：

```bash
cp skill.md ~/.claude/skills/law-paper-review/skill.md
```

或者直接克隆本仓库：

```bash
git clone https://github.com/wuwanqiang/law-paper-review-skill.git
cp law-paper-review-skill/skill.md ~/.claude/skills/law-paper-review/skill.md
```

## 使用方法

在 Claude Code 中直接说：

```
帮我审查这篇论文 /path/to/your/paper.docx
```

支持的触发词：
- 审查论文、论文自查、帮我审稿
- review paper、paper review、check my paper
- 投稿前检查、论文检查

支持的文件格式：**PDF、DOCX、Markdown、纯文本**

## 输出示例

审查完成后会生成结构化的综合报告，包含：

- 总体评估（⭐评分 + 投稿就绪度）
- 8 位专家的审查摘要
- 优先修改清单（🔴🟡🟢三级标注）
- 分阶段修改路线图

## 注意事项

- 8 个并行 agent 每次运行会消耗较多 token（约 40 万+）
- 如需降低成本，可在 skill.md 中将 Task 的 model 参数改为 `"sonnet"` 或 `"haiku"`
- 论文越长，消耗的 token 越多（因为每个 agent 都需要接收完整论文内容）

## 自定义

你可以根据自己的学科方向修改 `skill.md`：
- 调整专家角色和审查维度
- 增减专家数量（不一定要 8 个）
- 修改触发词
- 调整输出报告的格式

## License

MIT
