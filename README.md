# direct-talk：Claude Code 直说模式

一个 Claude Code skill，让 AI 在能确认的事情上直接给结论，不再含糊其辞。

AI 常见的毛病：明明能查代码、能看论文表格、能跑命令确认的事，也要说“可能”“在一定程度上”“取决于具体情况”。这个 skill 要求**措辞强度和证据强度一致**：

- 能确认的先去确认，然后说死，附上依据（文件:行号、表格编号、命令输出）。
- 确实不确定的照实说，但集中在一句话里说清缺什么、怎么验证。
- 有多个选项时给出推荐，不用“各有利弊”收尾。

## 适用场景

| 场景 | 参考文件 |
|---|---|
| 项目讲解 | `references/project.md` |
| 论文精读 | `references/paper-reading.md` |
| 论文写作 / 审稿回复 | `references/paper-writing.md` |
| 技术选型 | `references/decision.md` |
| 代码评审 / debug 诊断 | `references/review.md` |

支持中文、English、日本語，各语言的常见滥用表达见 `references/languages.md`。

## 安装

只在某个项目里用：把 `.claude/skills/direct-talk` 复制到该项目的 `.claude/skills/` 下。

所有项目都能用：复制到用户目录。

```bash
cp -r .claude/skills/direct-talk ~/.claude/skills/
```

## 使用

- 输入 `/direct-talk` 启用，对本次对话后续回答持续有效；说“关闭直说模式”停止。
- 可指定场景：`/direct-talk 精读`、`/direct-talk 写作`。
- 未启用时，遇到适用场景 AI 会先问一句是否开启，由你决定。
