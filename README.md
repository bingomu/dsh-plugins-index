# DSH 插件市场索引（Genzo）

给 DeepSeek Harness「插件 → 插件市场 → 发现」用的索引文件，格式 1。

**索引地址**

```
https://raw.githubusercontent.com/bingomu/dsh-plugins-index/main/index.json
```

在 DSH 里添加：插件 → 发现 → 添加索引源 → 粘贴上面的 URL → 添加。

## 里面有什么

| 插件 | 版本 |
|---|---|
| `@bingomu/dsh-wingman` 对话工具条 | 1.0.3 |
| `@bingomu/dsh-followup` 跟进清单 | 0.2.4 |
| `dsh-sticky-wall` 便签墙 | 1.1.1 |
| `@bingomu/dsh-usage-printer` 用量小票机 | 1.4.0 |
| `dsh-image-zoom` 图片查看器 | 1.0.1 |
| `dsh-readable-diagrams` 可读图表 | 1.1.0 |

## 发新版后要改哪里

`index.json` 里对应插件的 `versions[0]`：

- `version`：新版本号
- `publishTimestamp`：Release 的发布时间（Unix 秒）
- `source.commit`：该 tag 的 40 位 commit SHA
- `icon` 如果 icon 换了，也跟着换路径

格式由 `@deepseek-ai/dsh-plugin-market-index` 校验；改完可以用它验一遍（`parseMarketIndex`）。

## 格式

```json
{
  "format": 1,
  "title": { "zh": "...", "en": "..." },
  "plugins": [
    {
      "name": "@scope/pkg",
      "title": { "zh": "...", "en": "..." },
      "versions": [
        { "version": "1.0.0", "publishTimestamp": 1794123456,
          "source": { "type": "git", "url": "https://github.com/owner/repo", "commit": "<40 hex>" },
          "engines": { "dsh": ">=0.2.1-rc.5 <0.3.0-0" } }
      ]
    }
  ]
}
```
