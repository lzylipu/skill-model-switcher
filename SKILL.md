---
name: model-switcher
description: "Switch between fast and deep models (OpenClaw legacy - use Hermes provider config instead)"
version: 1.0.0
author: lzylipu
license: MIT
platforms: [linux]
status: legacy
note: "Designed for OpenClaw. Hermes Agent uses provider/profile config for model switching"
metadata:
  hermes:
    tags: [model, switch, deepseek, flash, pro, 模型, 切换]
    related_skills: []
    homepage: https://github.com/lzylipu/openclaw-skill-model-switcher
    category: personal
    skill_type: config
---

> **Note**: This skill was designed for OpenClaw. Hermes Agent uses `hermes config set` or the Web UI provider settings for model switching.

# Model Switcher / 模型切换器

## 概述

主用 DeepSeek V4-Flash（快速响应日常对话），备用 DeepSeek V4-Pro（深度推理，适用于代码编写、复杂分析、长文档处理）。根据任务类型自动选择合适模型。

## 模型配置

| 模型 | 角色 | 适用场景 |
|------|------|----------|
| **deepseek-ai/deepseek-v4-flash** | 默认主模型 | 日常聊天、信息查询、简单处理 |
| **deepseek-ai/deepseek-v4-pro** | 备用深度模型 | 写代码、分析项目、长文本处理 |

## 默认模型切换

当用户要求"切换到 Pro"或"切回 Flash"时：
1. 修改 openclaw.json 中 `agents.defaults.models` 和 `agents.defaults.imageModel`
2. 热重载配置（`kill -HUP` openclaw 进程）

```json
// Flash 模式（日常）
"agents": {
  "defaults": {
    "models": { "custom-provider/deepseek-ai/deepseek-v4-flash": {} },
    "imageModel": "custom-provider/deepseek-ai/deepseek-v4-flash"
  }
}

// Pro 模式（深度任务）
"agents": {
  "defaults": {
    "models": { "custom-provider/deepseek-ai/deepseek-v4-pro": {} },
    "imageModel": "custom-provider/deepseek-ai/deepseek-v4-pro"
  }
}
```

## 任务类型判断

自动推荐 Pro 模式的任务特征：
- 用户提到"代码"、"debug"、"分析"、"重构"
- 需要多步骤执行的复杂任务
- 超过 1000 字的文本处理
- 需要精确推理的场景

默认使用 Flash 的场景：
- 信息查询、新闻摘要
- 日常对话、简短回复
- 简单文件操作

## 配置文件位置

`~/.openclaw/openclaw.json`