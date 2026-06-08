# ComfyUI 自定义节点开发 Skills

> 一套精心整理的 ComfyUI 自定义节点开发技能包。
> 兼容 **Claude Code**、**WorkBuddy (CodeBuddy)** 以及任何 **ClawHub** 兼容的 AI 编程助手。

[English](README.md)

---

## Skills 一览

| Skill | 触发场景 | 描述 |
|---|---|---|
| **comfyui-node-basics** | 创建节点、定义类、项目初始化 | V3 节点结构、`io.Schema`、输入/输出、`ComfyExtension` 注册 |
| **comfyui-node-inputs** | 配置控件、添加输入 | INT、FLOAT、STRING、BOOLEAN、COMBO、隐藏/可选/惰性输入、`force_input` |
| **comfyui-node-outputs** | 返回结果、预览、保存文件 | `NodeOutput`、`PreviewImage/Mask/Audio/Text`、`SavedImages`、UI 辅助 |
| **comfyui-node-datatypes** | 处理张量、模型类型 | IMAGE、LATENT、MASK、CONDITIONING、MODEL、CLIP、VAE、AUDIO、VIDEO、3D、自定义类型 |
| **comfyui-node-advanced** | 动态输入、类型匹配、节点展开 | MatchType、Autogrow、DynamicCombo、`GraphBuilder`、MultiType、异步 |
| **comfyui-node-lifecycle** | 执行调试、缓存、校验 | `fingerprint_inputs`、`validate_inputs`、`check_lazy_status`、执行顺序 |
| **comfyui-node-frontend** | UI 功能、自定义控件、扩展 | JS 生命周期钩子、侧边栏、命令、设置、Toast、对话框、右键菜单 |
| **comfyui-node-migration** | V1 节点迁移至 V3 | 属性映射、方法转换、注册方式变更 |
| **comfyui-node-packaging** | 项目搭建、发布 | 目录结构、`__init__.py`、`pyproject.toml`、`WEB_DIRECTORY`、Registry 发布 |

---

## 安装方式

### 1. WorkBuddy / CodeBuddy（推荐）

**通过技能广场安装**（即将上线）：
在 WorkBuddy 技能广场中搜索 `comfyui-node-*`，一键安装。

**手动安装（全局）**：
```bash
git clone https://github.com/xujianjian2004/comfyui-custom-node-skills.git
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* ~/.workbuddy/skills/
```

**项目级安装**：
```bash
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* /path/to/your-project/.workbuddy/skills/
```

### 2. Claude Code

**通过插件市场（推荐）**：
在 Claude Code 中添加仓库 URL，安装 `comfyui-custom-nodes` 插件，自动包含全部 9 个 Skills。

**手动安装**：
```bash
git clone https://github.com/xujianjian2004/comfyui-custom-node-skills.git
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* ~/.claude/skills/
```

### 验证安装

检测到相关上下文时，Skills 会自动加载。也可手动确认：

- **WorkBuddy**：左侧边栏「技能」中查看已安装 Skills
- **Claude Code**：运行 `/skills`

---

## 使用示例

```
"创建一个带有图像输入和浮点滑块的基本 V3 节点"
→ 使用 comfyui-node-basics + comfyui-node-inputs

"为我的节点添加预览图像输出"
→ 使用 comfyui-node-outputs

"将我的 V1 节点迁移到 V3"
→ 使用 comfyui-node-migration

"添加一个带有自定义设置的侧边栏标签"
→ 使用 comfyui-node-frontend
```

---

## WorkBuddy 专属增强

此版本新增了以下字段，以优化 WorkBuddy 集成体验：

| 增强项 | 说明 |
|---|---|
| `description_zh` | 全部 9 个 Skill 的中文描述 |
| `agent_created: true` | 标记为 Agent 管理，确保正确的生命周期 |
| `version: "1.0.0"` | 语义化版本号，支持依赖追踪 |
| `LICENSE.txt` | 每个 Skill 目录内含 MIT 协议副本 |

---

## 核心特点

- **V3 API 优先** — 所有示例使用现代 V3 API（`io.ComfyNode`、`io.Schema`、`io.NodeOutput`）
- **V1 参考保留** — 旧版文档完整保留，方便迁移和向后兼容
- **源码验证** — 与 ComfyUI 前后端实际源码交叉比对
- **覆盖全面** — 从基础节点创建到 DynamicCombo、节点扩展等高级模式
- **前端扩展** — 完整的 JavaScript 扩展系统，包含 **15+ 生命周期钩子**
- **多平台兼容** — 同时支持 Claude Code、WorkBuddy（CodeBuddy）和 ClawHub

---

## 数据来源

基于以下源码构建并验证：

| 来源 | 说明 | 最后验证版本 |
|---|---|---|
| [ComfyUI 后端](https://github.com/comfyanonymous/ComfyUI) | V3 API 位于 `comfy_api/latest/`，V1 位于 `comfy/comfy_types/` | `a2840e75` |
| [ComfyUI 前端](https://github.com/Comfy-Org/ComfyUI_frontend) | 扩展系统、控件类型、设置 | `6f579c59` |
| [ComfyUI 文档](https://docs.comfy.org/custom-nodes/overview) | 官方指南和参考资料 | — |
| 内置节点实现 | `comfy_extras/` 目录下的节点实现 | — |

---

## 许可证

**MIT** — Copyright (c) jtydhr88
WorkBuddy版｜由WOSAI STUDIO 穿山阅海 改造
详见 [LICENSE](LICENSE) 文件。
