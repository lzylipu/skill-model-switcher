# 🔀 Model Switcher / 智能大模型切换器

> 🌐 English | [简体中文](./README.md)
> **Deprecated Notice**: Built for legacy OpenClaw architectures. For Hermes Agent, please switch models directly using provider/profile settings.
> **弃用说明**: 此技能为 OpenClaw 构建。在 Hermes Agent 下，请直接使用系统的 provider/profile 配置切换模型。

---

## 📖 简介 / Overview

- **English**: Intelligent LLM routing selector to swap between DeepSeek V4-Flash (for lightweight queries) and DeepSeek V4-Pro (for reasoning and execution).
- **中文**: 智能大模型路由选择器，根据任务的复杂度自动在快速响应的 DeepSeek V4-Flash 与强力推理的 V4-Pro 之间进行一键式模型热切换。

## ✨ 特性 / Features

- ⚡ **Lightweight mode / 日常模式**: Swaps to DS-Flash for rapid responses and speed-oriented tasks. / 遇到常规对话任务自动切换为 Flash，以毫秒级响应见长。
- 🧠 **Reasoning mode / 深度模式**: Swaps to DS-Pro automatically for deep thinking, programming, and debugging. / 遇到代码审查、推理等复杂工作自动切换为 Pro 模型。
- 🤖 **Auto routing / 自动路由**: Real-time evaluation of task complexity. / 动态任务复杂度自动监测。

## 📁 目录结构 / Project Structure

```
skill-model-switcher/
├── SKILL.md                  # 技能定义文件 / Skill Definition
└── README.md                 # 说明文档 / Documentation
```

## 📄 许可证 / License

MIT License
