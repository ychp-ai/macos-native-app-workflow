# macos-native-app-workflow

macOS 原生应用开发 Skill，采用与 wechat-miniprogram-workflow 一致的单入口、子命令和按需参考结构。共 13 个业务子命令，另有 help。可独立执行任一节点。

仓库：git@github.com:ychp-ai/macos-native-app-workflow.git

## 调用

在 Codex 对话中输入（不是终端命令）：

```text
$macos-native-app-workflow help
$macos-native-app-workflow requirements 梳理一个菜单栏待办应用的首版需求。
$macos-native-app-workflow scaffold 创建 SwiftUI 项目，支持主窗口和设置窗口。
$macos-native-app-workflow feature 实现文件导入与取消操作。
$macos-native-app-workflow optimize 只分析导入卡顿的原因，不修改代码。
$macos-native-app-workflow redesign 重新设计并实现设置窗口，保留已有选项。
$macos-native-app-workflow windows 修复关闭主窗口后无法重新打开的问题。
$macos-native-app-workflow debug 排查启动崩溃并修复。
$macos-native-app-workflow verify 只验证文件导入流程，不修改代码。
$macos-native-app-workflow signing 检查现有 app 的签名与权限，不修改产物。
$macos-native-app-workflow release 只准备 Developer ID 分发，不提交公证。
```

组合执行需要明确指定：

```text
使用 $macos-native-app-workflow，依次执行 requirements、design，完成后停止。
```

## 子命令

| 子命令 | 能力 | 说明 |
|---|---|---|
| `requirements` | 需求梳理 | [requirements.md](references/requirements.md) |
| `design` | 原生 UI 设计 | [design.md](references/design.md) |
| `scaffold` | 项目搭建 | [scaffold.md](references/scaffold.md) |
| `feature` | 功能开发 | [feature.md](references/feature.md) |
| `optimize` | 现有功能优化 | [optimize.md](references/optimize.md) |
| `redesign` | 页面与窗口重设计 | [redesign.md](references/redesign.md) |
| `windows` | 窗口与菜单栏 | [windows.md](references/windows.md) |
| `motion` | 原生动效 | [motion.md](references/motion.md) |
| `polish` | 界面打磨 | [polish.md](references/polish.md) |
| `debug` | 构建运行与调试 | [debug.md](references/debug.md) |
| `verify` | 测试验收 | [verify.md](references/verify.md) |
| `signing` | 签名与权限 | [signing.md](references/signing.md) |
| `release` | 打包与发布 | [release.md](references/release.md) |

## 关联技能

[入口映射](SKILL.md#显式关联技能) 明确各命令使用条件，[关联清单](references/skill-links.md) 列出 13 个技能的完整名称和职责。按需加载，执行时仅说明实际使用项与当前阻塞。

## 安装

本仓库整体是一个 Skill，包含 SKILL.md、agents/、references/。将其复制或软链到 `${CODEX_HOME:-$HOME/.codex}/skills/macos-native-app-workflow/`，新会话确认发现后调用。源码写入仓库不代表已安装。

未安装也可以直接指定本仓库 SKILL.md 的绝对路径，并要求执行某个子命令。

## 执行与交付

沿用目标项目的 SwiftUI/AppKit、Xcode/SwiftPM 与最低系统版本。只分析、只设计或实现由请求决定。报告默认写入项目 docs/macos/，只读请求在对话交付。

本地构建、GUI 运行、测试、签名、公证和公开发布是不同阶段。工具、真实证书与账号权限需实际可用，结论以执行证据为准。
