# My Blog

个人博客仓库，存放文章与交易笔记。笔记按分类归档到 `posts/` 下的不同文件夹，每篇笔记开头带 YAML front matter（元信息）。

## 目录结构

```
MyBlog/
├── README.md          # 本文件：写作约定与分类说明
├── templates/         # 笔记模板（写笔记前先复制对应模板）
│   ├── note.md        # 通用笔记模板
│   └── review.md      # 交易复盘模板
└── posts/             # 笔记按分类归档到对应文件夹
    ├── 交易理念/      # 交易心理、盈利本质、课程笔记
    ├── 策略研究/      # 具体策略、战法、方法
    ├── 市场分析/      # 行情观点、市场评论
    ├── 复盘/          # 单笔交易复盘（type: review）
    └── 随笔/          # 非交易类随笔
```

## 分类体系

| 文件夹 | front matter 标记 | 用途 |
|--------|------------------|------|
| `交易理念/` | `type: note` + `category: 交易理念` | 交易心理、盈利本质、课程笔记 |
| `策略研究/` | `type: note` + `category: 策略研究` | 具体策略、战法、方法 |
| `市场分析/` | `type: note` + `category: 市场分析` | 行情观点、市场评论 |
| `复盘/` | `type: review` | 单笔交易复盘 |
| `随笔/` | `type: note` + `category: 随笔` | 非交易类随笔 |

## 元信息规范（front matter）

每篇笔记开头必须包含 YAML front matter，放在两个 `---` 之间。两类笔记对应两个模板：

### 通用笔记（`type: note`）

```markdown
---
title: "标题"
date: 2026-08-05
type: note
category: "策略研究"   # 交易理念 / 策略研究 / 市场分析 / 随笔
source: ""            # 可选：来源链接
tags:
  - 追涨
---
```

### 交易复盘（`type: review`）

```markdown
---
title: "BTC震荡偏空"
date: 2026-08-03
type: review
instrument: "BTC"
method: ""
entry_pattern: ""
timeframe: "1h"
market_cycle: "震荡"
trade_type: ""
tags:
  - 假设单
direction: short
result: loss
pnl_r: ""
pnl: 4
confidence: 1
summary: "在震荡区间上部分开空"
---
```

`result` 取值：`win` / `loss` / `breakeven`；`direction` 取值：`long` / `short`；`confidence` 取值 1-5。

## 写作流程

1. **确定分类**：这篇笔记属于哪一类（交易理念 / 策略研究 / 市场分析 / 复盘 / 随笔）。
2. **复制模板**：从 `templates/` 复制对应模板（普通笔记用 `note.md`，交易复盘用 `review.md`）。
3. **填元信息**：填写 title / date / category（复盘填 instrument 等交易字段）/ tags。
4. **命名文件**：文件名用 `YYYY-MM-DD-标题.md` 格式，便于按时间排序。
5. **归档**：放入 `posts/` 下对应的分类文件夹。

> 模板里的 `#` 注释是填写提示，正式笔记里不必保留这些注释。
