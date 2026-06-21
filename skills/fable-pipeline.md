---
name: fable-pipeline
description: 知识管线操作 — 运行、调试、扩展 knowledge-pipeline 的抓取→分类→去重→改写流程。触发词：跑管线、抓取、pipeline、知识引擎。
---

# 知识管线操作

## When to Use

- 用户说"跑一下管线""抓点内容""更新知识库"
- 需要从B站/知乎/公众号抓取新内容
- 调试管线某个环节（分类不准、改写不对味）
- 添加新平台或新关键词

## How It Works

### 管线架构速查

```
抓取 (B站/知乎/公众号) → 分类 (8大类50+子类) → 去重 (SQLite) → 质量过滤 (两阶段) → 景一改写 → Obsidian输出
```

### 常用操作

**预览运行（不写入）**：
```bash
cd knowledge-pipeline && python main.py --dry-run
```

**指定平台**：
```bash
python main.py --platform bilibili
python main.py --platform zhihu
```

**调试模式（禁用并发，便于观察）**：
```bash
python main.py --no-parallel --dry-run
```

**自定义输出路径**：
```bash
python main.py --vault /path/to/obsidian/vault
```

### 配置调整

- **关键词** → `config/platforms.yaml`
- **分类体系** → `config/categories.yaml`
- **改写prompt** → `config/prompts/humanize.txt`
- **质量阈值** → `config/categories.yaml` 中的 quality 字段

### 添加新平台

1. 在 `src/scrapers/` 创建新文件，继承 `BaseScraper`
2. 实现 `platform_name` 和 `search_keywords()`
3. 在 `src/main.py` 的 `scrapers_map` 中注册
4. 在 `config/platforms.yaml` 添加配置

## 管线健康检查

定期检查：
- `data/seen_urls.db` 大小是否异常（去重库膨胀）
- `logs/pipeline_*.log` 最新运行日志有无报错
- API 额度是否充足
- 改写产出质量是否稳定（随机抽检3篇）
