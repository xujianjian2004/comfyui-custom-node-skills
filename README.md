# ComfyUI Custom Node Skills

> A curated collection of skills for developing **ComfyUI custom nodes**.
> Compatible with **Claude Code**, **WorkBuddy (CodeBuddy)**, and any **ClawHub**-compatible AI coding agent.

[中文说明](README_ZH.md)

---

## Skills Overview

| Skill | Triggers | Description |
|---|---|---|
| **comfyui-node-basics** | Creating nodes, defining classes, project setup | V3 node structure, `io.Schema`, inputs/outputs, `ComfyExtension` registration |
| **comfyui-node-inputs** | Configuring widgets, adding inputs | INT, FLOAT, STRING, BOOLEAN, COMBO, hidden/optional/lazy inputs, `force_input` |
| **comfyui-node-outputs** | Returning results, previews, saving files | `NodeOutput`, `PreviewImage/Mask/Audio/Text`, `SavedImages`, UI helpers |
| **comfyui-node-datatypes** | Working with tensors, model types | IMAGE, LATENT, MASK, CONDITIONING, MODEL, CLIP, VAE, AUDIO, VIDEO, 3D, custom types |
| **comfyui-node-advanced** | Dynamic inputs, type matching, expansion | MatchType, Autogrow, DynamicCombo, `GraphBuilder`, MultiType, async |
| **comfyui-node-lifecycle** | Debugging execution, caching, validation | `fingerprint_inputs`, `validate_inputs`, `check_lazy_status`, execution order |
| **comfyui-node-frontend** | UI features, custom widgets, extensions | JS hooks, sidebar tabs, commands, settings, toasts, dialogs, context menus |
| **comfyui-node-migration** | Converting V1 nodes to V3 | Property mapping, method conversion, registration changes |
| **comfyui-node-packaging** | Project setup, publishing | Directory layout, `__init__.py`, `pyproject.toml`, `WEB_DIRECTORY`, registry publishing |

---

## Installation

### 1. WorkBuddy / CodeBuddy (Recommended)

**Via Skills Marketplace** (coming soon):
Search for `comfyui-node-*` in the WorkBuddy Skills Marketplace and install with one click.

**Manual installation** (all projects):
```bash
git clone https://github.com/xujianjian2004/comfyui-custom-node-skills.git
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* ~/.workbuddy/skills/
```

**Project-specific**:
```bash
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* /path/to/your-project/.workbuddy/skills/
```

### 2. Claude Code

**Via Plugin Marketplace** (Recommended):
Add this repository URL in Claude Code's marketplace. Installs the `comfyui-custom-nodes` plugin with all 9 skills.

**Manual installation**:
```bash
git clone https://github.com/xujianjian2004/comfyui-custom-node-skills.git
cp -r comfyui-custom-node-skills/plugins/comfyui-custom-nodes/skills/comfyui-node-* ~/.claude/skills/
```

### Verification

Skills load automatically when relevant context is detected. You can also check availability:

- **WorkBuddy**: Skills appear in the left sidebar under "Skills"
- **Claude Code**: Run `/skills`

---

## Usage Examples

```
"Create a basic V3 node with an image input and a float slider"
→ Uses comfyui-node-basics + comfyui-node-inputs

"Add a preview image output to my node"
→ Uses comfyui-node-outputs

"Migrate my V1 node to V3"
→ Uses comfyui-node-migration

"Add a sidebar tab with custom settings"
→ Uses comfyui-node-frontend
```

---

## WorkBuddy-Specific Enhancements

This fork/maintained version includes additional fields for optimal WorkBuddy integration:

| Enhancement | Description |
|---|---|
| `description_zh` | Chinese descriptions for all 9 skills |
| `agent_created: true` | Marks skills as agent-managed for proper lifecycle |
| `version: "1.0.0"` | Semantic versioning for dependency tracking |
| `LICENSE.txt` | Explicit MIT license copy in each skill directory |

---

## Key Features

- **V3 API First** — All examples use the modern V3 API (`io.ComfyNode`, `io.Schema`, `io.NodeOutput`)
- **V1 Reference** — Legacy V1 patterns documented for migration and backward compatibility
- **Source-Verified** — Cross-referenced against actual ComfyUI backend and frontend source code
- **Full Coverage** — From basic node creation to advanced patterns like DynamicCombo and node expansion
- **Frontend Extensions** — Complete JavaScript extension system with **15+ lifecycle hooks**
- **Multi-Platform** — Compatible with Claude Code, WorkBuddy (CodeBuddy), and ClawHub

---

## Sources

Built and verified against:

| Source | Description | Last Verified |
|---|---|---|
| [ComfyUI backend](https://github.com/comfyanonymous/ComfyUI) | V3 API in `comfy_api/latest/`, V1 in `comfy/comfy_types/` | `a2840e75` |
| [ComfyUI frontend](https://github.com/Comfy-Org/ComfyUI_frontend) | Extension system, widget types, settings | `6f579c59` |
| [ComfyUI docs](https://docs.comfy.org/custom-nodes/overview) | Official guides and references | — |
| Built-in node implementations | Nodes in `comfy_extras/` | — |

---

## License

**MIT** — Copyright (c) jtydhr88
WorkBuddy版｜由WOSAI STUDIO 穿山阅海 改造
See [LICENSE](LICENSE) for full text.
