# 🦞 reatang-skills Marketplace

个人技能市场 - 符合 Claude Code Plugin Marketplace 标准

## 结构

```
reatang-skills/
├── .claude-plugin/
│   └── marketplace.json    # Marketplace 索引（Claude Code 标准）
└── plugins/
    └── <plugin-name>/      # 每个插件独立目录
        ├── .claude-plugin/
        │   └── plugin.json # 插件 manifest
        ├── skills/         # 技能目录
        │   └── <skill>/
        │       └── SKILL.md
        ├── agents/         # 子代理（可选）
        ├── hooks/          # 钩子配置（可选）
        └── .mcp.json       # MCP 服务器（可选）
```

## Marketplace Schema

`marketplace.json` 必需字段：

| 字段 | 类型 | 说明 |
|------|------|------|
| `name` | string | Marketplace ID（kebab-case） |
| `owner` | object | 维护者信息（`name` 必需，`email` 可选） |
| `plugins` | array | 插件列表 |

每个插件 entry 必需：

| 字段 | 类型 | 说明 |
|------|------|------|
| `name` | string | 插件 ID |
| `source` | string/object | 来源路径 |

## 使用方式

### 添加 Marketplace

```bash
/plugin marketplace add https://github.com/reatang/reatang-skills.git
```

### 安装插件

```bash
/plugin install <plugin-name>@reatang-skills
```

### 更新

```bash
/plugin marketplace update reatang-skills
```

## Plugin Manifest Schema

每个插件的 `plugin.json`：

```json
{
  "name": "plugin-name",
  "description": "简短描述",
  "version": "1.0.0",
  "author": {
    "name": "reatang"
  }
}
```

## 已发布插件

（待添加）

---

_Maintained by @reatang_  
_Follows [Claude Code Plugin Marketplace Standard](https://code.claude.com/docs/en/plugin-marketplaces)_