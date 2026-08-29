# My Blog

个人博客仓库，存放文章与交易笔记。笔记按「大类 → 子类」两层文件夹归档，每篇笔记开头带 YAML front matter（元信息）。

## 目录结构

```
MyBlog/
├── README.md          # 本文件：写作约定与分类说明
├── templates/         # 笔记模板（写笔记前先复制对应模板）
│   ├── note.md        # 通用笔记模板
│   └── review.md      # 交易复盘模板
└── posts/             # 按「大类/子类」归档
    ├── 投资/          # 投资大类
    │   ├── 交易理念/  # 交易心理、盈利本质、课程笔记
    │   ├── 策略研究/  # 具体策略、战法、方法
    │   ├── 市场分析/  # 行情观点、市场评论
    │   └── 复盘/      # 单笔交易复盘（type: review）
    └── 随笔/          # 非投资类随笔（其它大类可另建顶级文件夹）
```

## 分类体系

`category` 字段 = 相对 `posts/` 的文件夹路径，用 `/` 分隔大类与子类。

| 文件夹 | front matter 标记 | 用途 |
|--------|------------------|------|
| `投资/交易理念/` | `type: note` + `category: "投资/交易理念"` | 交易心理、盈利本质、课程笔记 |
| `投资/策略研究/` | `type: note` + `category: "投资/策略研究"` | 具体策略、战法、方法 |
| `投资/市场分析/` | `type: note` + `category: "投资/市场分析"` | 行情观点、市场评论 |
| `投资/复盘/` | `type: review` | 单笔交易复盘 |
| `随笔/` | `type: note` + `category: "随笔"` | 非投资类随笔 |

**扩展新大类**：写其它类型笔记时，在 `posts/` 下新建顶级大类文件夹（如 `生活/`、`技术/`），子类用 `大类/子类` 路径，如 `category: "生活/读书"`。

## 元信息规范（front matter）

每篇笔记开头必须包含 YAML front matter，放在两个 `---` 之间。两类笔记对应两个模板：

### 通用笔记（`type: note`）

```markdown
---
title: "标题"
date: 2026-08-05
type: note
category: "投资/策略研究"   # = 文件夹路径，如 投资/交易理念 / 生活/读书 / 随笔
source: ""               # 可选：来源链接
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

1. **确定分类**：这篇笔记属于哪个大类/子类（投资/交易理念、投资/策略研究、生活/读书……）。
2. **复制模板**：从 `templates/` 复制对应模板（普通笔记用 `note.md`，交易复盘用 `review.md`）。
3. **填元信息**：填写 title / date / category（复盘填 instrument 等交易字段）/ tags。
4. **命名文件**：文件名用 `YYYY-MM-DD-标题.md` 格式，便于按时间排序。
5. **归档**：放入 `posts/` 下对应的分类文件夹（路径与 category 字段一致）。

> 模板里的 `#` 注释是填写提示，正式笔记里不必保留这些注释。
