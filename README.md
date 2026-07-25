# My Blog

个人博客仓库,用于存放文章与后续搭建博客网站。

## 目录结构

- `posts/` — 存放博客文章(Markdown 格式)
- `README.md` — 仓库说明

## 使用方式

1. 把写好的文章(`.md` 文件)放入 `posts/` 目录。
2. 后续选定静态博客框架(如 Jekyll / Hugo / Hexo)后,再补充配置文件与主题。
3. 通过 GitHub Pages 或其他服务部署为博客网站。

## 写作约定(建议)

文章文件名建议采用 `YYYY-MM-DD-标题.md` 格式,便于按时间排序,例如:

```
posts/2026-07-25-hello-world.md
```

每篇文章可在开头加上简单的元信息(front matter),方便日后框架识别:

```markdown
---
title: 文章标题
date: 2026-07-25
tags: [随笔]
---

正文内容……
```
