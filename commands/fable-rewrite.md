---
description: 用景一风格改写内容 — 一句话触发冶炼引擎
---

# /fable-rewrite

## 用法

```
/fable-rewrite <内容或文件路径>
```

## 示例

```
/fable-rewrite 这篇文章讲的是AI如何改变教育…
/fable-rewrite ~/Downloads/article.md
/fable-rewrite https://mp.weixin.qq.com/s/xxxxx
```

## 执行流程

1. 加载 `fable-style` 技能中的风格DNA
2. 如果是URL，先抓取原文
3. 如果原文已有风格（如公众号文章），先提取核心信息
4. 按冶炼算法改写：反常识钩子 → 心理×国学 → 场景 → 金句
5. 自检冶炼标准4条
6. 输出改写结果 + 即梦提示词 + 变现方向

## 相关

- `fable-style` 技能 — 完整风格定义
- `fable-brainstorm` 技能 — 选题角度挖掘
