---
description: 一键触发知识管线（抓取→分类→改写→输出）
---

# /fable-pipeline

## 用法

```
/fable-pipeline [--dry-run] [--platform <name>]
```

## 示例

```
/fable-pipeline                    # 完整运行
/fable-pipeline --dry-run          # 预览模式
/fable-pipeline --platform bilibili # 只抓B站
/fable-pipeline --status           # 查看管线状态
/fable-pipeline --check-health     # 健康检查
```

## 执行流程

1. 确认 knowledge-pipeline 目录可访问
2. 检查 API 密钥和配置
3. 执行管线（或在预览模式下展示将执行的操作）
4. 汇总结果：抓取数、通过质量过滤数、已改写数
5. 随机抽检1-2篇改写质量

## 相关

- `fable-pipeline` 技能 — 管线架构和调试指南
- `knowledge-pipeline` 仓库 — 管线源代码
